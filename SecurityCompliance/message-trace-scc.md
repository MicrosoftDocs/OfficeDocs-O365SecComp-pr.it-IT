---
title: Traccia dei messaggi in & la sicurezza centro conformità
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: Gli amministratori possono usare traccia dei messaggi in & la sicurezza centro conformità per scoprire Dov'ai messaggi.
ms.openlocfilehash: 9dfdab4adc5caba55664e93b49c8428791670ab3
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685507"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="80be7-103">Traccia dei messaggi in & la sicurezza centro conformità</span><span class="sxs-lookup"><span data-stu-id="80be7-103">Message trace in the Security & Compliance Center</span></span>

<span data-ttu-id="80be7-p101">Traccia dei messaggi in & la sicurezza centro conformità segue messaggi di posta elettronica quando passano attraverso l'organizzazione Exchange Online. È possibile determinare se un messaggio è stato ricevuto, rifiutato, rinviato o distribuito tramite il servizio. Viene inoltre le azioni eseguite nel messaggio prima che raggiunto il relativo stato finale.</span><span class="sxs-lookup"><span data-stu-id="80be7-p101">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization. You can determine if a message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="80be7-p102">Traccia dei messaggi in & la sicurezza centro conformità migliora traccia dei messaggi che è stato disponibile nell'interfaccia di amministrazione di Exchange (EAC). È possibile utilizzare le informazioni di traccia dei messaggi per rispondere alle domande utente sulle modifiche apportate alle loro messaggi funzionalità, risoluzione dei problemi del flusso di posta elettronica e convalidare le modifiche ai criteri in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="80be7-p102">Message trace in the Security & Compliance Center improves upon message trace that was available in the Exchange admin center (EAC). You can use the information from message trace to efficiently answer user questions about what happened to their messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="80be7-109">Traccia messaggio aperto</span><span class="sxs-lookup"><span data-stu-id="80be7-109">Open message trace</span></span>

1. <span data-ttu-id="80be7-110">[Accedere a Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con il proprio account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="80be7-110">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="80be7-111">Selezionare l'icona di avvio delle app ![Icona di avvio delle app di Office 365](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) nell'angolo in alto a sinistra e scegliere **Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="80be7-111">Select the app launcher icon ![Office 365 app launcher icon](media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="80be7-112">Nel riquadro di spostamento, in basso a sinistra espandere **Admin Center** e selezionare **& Security Compliance**.</span><span class="sxs-lookup"><span data-stu-id="80be7-112">In the lower-left navigation, expand **Admin centers** and select **Security & Compliance**.</span></span>

4. <span data-ttu-id="80be7-113">Nella pagina **sicurezza & conformità** visualizzata, espandere **il flusso della posta**e selezionare **traccia dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="80be7-113">In the **Security & Compliance** page that opens, expand **Mail flow**, and select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="80be7-114">Pagina di traccia messaggio</span><span class="sxs-lookup"><span data-stu-id="80be7-114">Message trace page</span></span>

<span data-ttu-id="80be7-p103">Da qui è possibile avviare una nuova traccia predefinito facendo clic sul pulsante **Start una traccia** . In questo cercherà per tutti i messaggi per tutti i mittenti e destinatari ultimi due giorni. Oppure è possibile utilizzare una delle query archiviate dalle categorie di query disponibili e uno eseguirli come-è o utilizzarli come punto di partenza per le query:</span><span class="sxs-lookup"><span data-stu-id="80be7-p103">From here you can start a new default trace by clicking on the **Start a trace** button. This will search for all messages for all senders and recipients for the last two days. Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="80be7-118">**Predefinito delle query**: query predefinita fornita da Office 365.</span><span class="sxs-lookup"><span data-stu-id="80be7-118">**Default queries**: Built-in queries provided by Office 365.</span></span>

- <span data-ttu-id="80be7-119">**Le query personalizzate**: query salvate dagli amministratori dell'organizzazione per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="80be7-119">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="80be7-p104">**Query salvata automaticamente**: più di recente dieci ultimi eseguono di query. In questo elenco rende più semplice sollevare di cui è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="80be7-p104">**Autosaved queries**: The last ten most recently run queries. This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="80be7-122">In questa pagina è inoltre una sezione di **report Downloadable** per le richieste inviate, nonché i report stessi quando sono disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="80be7-122">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="80be7-123">Opzioni per la nuova traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="80be7-123">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="80be7-124">Filtra per i mittenti e destinatari</span><span class="sxs-lookup"><span data-stu-id="80be7-124">Filter by senders and recipients</span></span>

<span data-ttu-id="80be7-125">I valori predefiniti sono **tutti i mittenti** e **tutti i destinatari**, ma è possibile utilizzare i campi seguenti per filtrare i risultati:</span><span class="sxs-lookup"><span data-stu-id="80be7-125">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="80be7-p105">**Da questi utenti**: fare clic su campo da selezionare uno o più mittenti dall'organizzazione. È inoltre possibile iniziare a digitare un nome e gli elementi nell'elenco verranno filtrati da quanto è stato digitato, molto simile comportamento di una pagina di ricerca.</span><span class="sxs-lookup"><span data-stu-id="80be7-p105">**By these people**: Click in this field to select one or more senders from your organization. You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="80be7-128">**Per queste persone**: fare clic su campo da selezionare uno o più destinatari nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80be7-128">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

<span data-ttu-id="80be7-p106">È inoltre possibile digitare gli indirizzi di posta elettronica di destinatari e mittenti esterni. I caratteri jolly sono supportate (`*@contoso.com` o `scot?@contoso.com`), ma non è possibile utilizzare più voci con caratteri jolly nello stesso campo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="80be7-p106">You can also type the email addresses of external senders and recipients. Wildcards are supported (`*@contoso.com` or `scot?@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>

### <a name="time-range"></a><span data-ttu-id="80be7-131">Intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="80be7-131">Time range</span></span>

<span data-ttu-id="80be7-p107">Il valore predefinito è **2 giorni**, ma è possibile specificare intervalli di data/ora di un massimo di 90 giorni. Quando si utilizzano gli intervalli di data/ora, prendere in considerazione questi problemi:</span><span class="sxs-lookup"><span data-stu-id="80be7-p107">The default value is **2 days**, but you can specify date/time ranges of up to 90 days. When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="80be7-p108">Per impostazione predefinita, si seleziona l'intervallo di tempo nella visualizzazione, **il dispositivo di scorrimento** utilizzando una linea di tempo. È possibile solo selezionare il giorno o ora di impostazioni che vengono visualizzate. Tentativo di selezionare un valore intermedi verrà bloccata bolla iniziale e finale per più vicino visualizzato impostazione.</span><span class="sxs-lookup"><span data-stu-id="80be7-p108">By default, you select the time range in **Slider** view using a time line. You can only select the day or time settings that are displayed. Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

   ![Un intervallo di tempo il dispositivo di scorrimento in una nuova traccia dei messaggi in & la sicurezza centro conformità](media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   <span data-ttu-id="80be7-p109">Tuttavia, è inoltre possibile passare alla visualizzazione di **personalizzato** dove è possibile specificare i valori di **Data di inizio** e **Data fine** (inclusi volte) ed è inoltre possibile selezionare il **fuso orario** per l'intervallo di data/ora. Si noti che l'impostazione del **fuso orario** si applica a entrambi gli input di query e risultati della query.</span><span class="sxs-lookup"><span data-stu-id="80be7-p109">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range. Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

   ![Un intervallo di tempo personalizzato in un nuovo traccia dei messaggi in & la sicurezza centro conformità](media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   <span data-ttu-id="80be7-p110">Per 10 giorni o meno i risultati sono disponibili immediatamente sotto forma di un rapporto di **Riepilogo** . Se si specifica un intervallo di tempo è leggermente maggiore di 10 giorni, i risultati verranno ritardi perché sono disponibili solo come file CSV scaricabile (report di **Riepilogo avanzata** o **estesa** ).</span><span class="sxs-lookup"><span data-stu-id="80be7-p110">For 10 days or less, the results are available instantly as a **Summary** report. If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

   <span data-ttu-id="80be7-143">Per ulteriori informazioni sui tipi di report diverso, vedere la sezione [scegliere il tipo di report](#choose-report-type) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="80be7-143">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

   <span data-ttu-id="80be7-p111">**Nota**: report di riepilogo ed estese avanzata vengono preparati utilizzando dati di traccia dei messaggi archiviati e potrebbe richiedere diverse ore prima che il report è disponibile per il download. In base al numero gli altri amministratori inoltre abbiano inviato le richieste di relazioni intorno alla stessa ora, è possibile notare un ritardo prima dell'avvio di elaborazione per le richieste in coda.</span><span class="sxs-lookup"><span data-stu-id="80be7-p111">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="80be7-p112">Salvataggio di una query nella visualizzazione **dispositivo di scorrimento** viene salvato l'intervallo di tempo relativo (ad esempio 3 giorni dalla data odierna). Salvataggio di una query nella visualizzazione **personalizzata** viene salvato l'intervallo di data/ora assoluto (ad esempio 2018-05-06 13:00 per 2018-05-08 18:00).</span><span class="sxs-lookup"><span data-stu-id="80be7-p112">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today). Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="80be7-148">Altre opzioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="80be7-148">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="80be7-149">Stato di recapito</span><span class="sxs-lookup"><span data-stu-id="80be7-149">Delivery status</span></span>

<span data-ttu-id="80be7-150">È possibile lasciare il valore predefinito **tutti** selezionata oppure è possibile selezionare uno dei seguenti valori per filtrare i risultati:</span><span class="sxs-lookup"><span data-stu-id="80be7-150">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="80be7-151">**Recapitati**: il messaggio è stato correttamente recapitato alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="80be7-151">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="80be7-152">**In sospeso**: recapito del messaggio è in corso tentativi o nuovi tentativi.</span><span class="sxs-lookup"><span data-stu-id="80be7-152">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="80be7-153">**Expanded**: un destinatario di gruppo di distribuzione è stata espansa prima del recapito per i singoli membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="80be7-153">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="80be7-154">**Errore**: Impossibile recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-154">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="80be7-p113">**In quarantena**: il messaggio è stato messo in quarantena (come posta indesiderata, posta inviata in blocco o phishing). Per ulteriori informazioni, vedere [i messaggi di posta elettronica quarantena in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span><span class="sxs-lookup"><span data-stu-id="80be7-p113">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing). For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/4c234874-015e-4768-8495-98fcccfc639b.aspx).</span></span>

- <span data-ttu-id="80be7-157">**Filtrato come posta indesiderata**: il messaggio è stato identificato posta indesiderata ed è stato rifiutato o bloccati (non in quarantena).</span><span class="sxs-lookup"><span data-stu-id="80be7-157">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="80be7-p114">**Recupero dello stato:** Il messaggio è stato ricevuto recentemente da Office 365, ma non gli altri dati sullo stato sono ancora disponibili. Controllare nuovamente in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="80be7-p114">**Getting status:** The message was recently received by Office 365, but no other status data is yet available. Check back in a few minutes.</span></span>

<span data-ttu-id="80be7-p115">**Nota**: I valori **in sospeso,** **in quarantena**e **Filtro posta indesiderata** sono disponibili solo per le ricerche di meno di 10 giorni. Inoltre, potrebbero verificarsi un ritardo da 5 a 10 minuti tra lo stato di recapito effettivo e segnalate.</span><span class="sxs-lookup"><span data-stu-id="80be7-p115">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days. Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="80be7-162">ID messaggio</span><span class="sxs-lookup"><span data-stu-id="80be7-162">Message ID</span></span>

<span data-ttu-id="80be7-p116">Questo è l'ID messaggio internet (detto anche ID Client) trovato nel **ID messaggio:** campo di intestazione nell'intestazione del messaggio. Gli utenti possono assegnare questo valore per analizzare i messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="80be7-p116">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header. Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="80be7-p117">Questo valore è costante per la durata del messaggio. Per i messaggi creati in Office 365 o Exchange, il valore è nel formato `<GUID@ServerFQDN>`, incluse le parentesi angolari (\< \>). Ad esempio `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Altri sistemi di messaggistica è possono utilizzare una sintassi diversa o valori. Questo valore deve per essere univoco, ma non tutti i sistemi di posta elettronica strettamente seguono questo requisito. Se il **ID messaggio:** campo di intestazione non esiste o è vuoto per i messaggi in arrivo provenienti da origini esterne, viene assegnato un valore arbitrario.</span><span class="sxs-lookup"><span data-stu-id="80be7-p117">This value is constant for the lifetime of the message. For messages created in Office 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>). For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Other messaging systems might use different syntax or values. This value is supposed to be unique, but not all email systems strictly follow this requirement. If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="80be7-171">Quando si utilizza **L'ID messaggio** per filtrare i risultati, assicurarsi di includere l'intera stringa, incluse le parentesi.</span><span class="sxs-lookup"><span data-stu-id="80be7-171">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="80be7-172">Direction</span><span class="sxs-lookup"><span data-stu-id="80be7-172">Direction</span></span>

<span data-ttu-id="80be7-173">È possibile lasciare il valore predefinito **tutti** selezionata oppure è possibile selezionare **in ingresso** (i messaggi inviati a destinatari nell'organizzazione) o **in uscita** (i messaggi inviati dagli utenti all'interno dell'organizzazione) per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="80be7-173">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="80be7-174">Indirizzo IP del client originale</span><span class="sxs-lookup"><span data-stu-id="80be7-174">Original client IP address</span></span>

<span data-ttu-id="80be7-p118">È possibile filtro i risultati dall'indirizzo IP del client per analizzare i computer violato l'invio di grandi quantità di posta indesiderata o malware. Anche se i messaggi potrebbero sembrare provenienti da mittenti multipli, è probabile che lo stesso computer sia la generazione di tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="80be7-p118">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware. Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="80be7-177">**Nota**: le informazioni sull'indirizzo IP client è disponibile solo per 10 giorni ed è disponibile solo nei rapporti di **Riepilogo avanzata** o **estesa** (con estensione CSV scaricabile).</span><span class="sxs-lookup"><span data-stu-id="80be7-177">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="80be7-178">Scelta del tipo di rapporto</span><span class="sxs-lookup"><span data-stu-id="80be7-178">Choose report type</span></span>

<span data-ttu-id="80be7-179">I tipi di report disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="80be7-179">The available report types are:</span></span>

- <span data-ttu-id="80be7-p119">**Riepilogo**: disponibile se l'intervallo di tempo è inferiore a 10 giorni e non richiede alcun ulteriori opzioni di filtro. I risultati sono disponibili quasi immediatamente dopo che si fa clic su **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="80be7-p119">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options. The results are available almost immediately after you click **Search**.</span></span>

- <span data-ttu-id="80be7-p120">**Riepilogo avanzata** o **estesa**: questi rapporti sono disponibili solo come file CSV scaricabili e richiedere una o più delle opzioni di filtro seguenti indipendentemente dall'intervallo di tempo: **da tali utenti**, **a queste persone**o \*\* ID messaggio\*\*. È possibile utilizzare i caratteri jolly per i mittenti o destinatari (ad esempio \*@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="80be7-p120">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**. You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span>

<span data-ttu-id="80be7-184">**Note**:</span><span class="sxs-lookup"><span data-stu-id="80be7-184">**Notes**:</span></span>

- <span data-ttu-id="80be7-p121">Rapporti di riepilogo ed estese avanzate vengono preparati utilizzando dati di traccia dei messaggi archiviati e potrebbe richiedere diverse ore prima che sia disponibile per il download del report. In base al numero gli altri amministratori inoltre abbiano inviato le richieste di relazioni intorno alla stessa ora, è possibile notare un ritardo prima dell'avvio da elaborare le richieste in coda.</span><span class="sxs-lookup"><span data-stu-id="80be7-p121">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download. Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="80be7-187">Mentre è possibile selezionare un rapporto di riepilogo o estese avanzata per qualsiasi intervallo di data/ora, comunemente ultimi quattro ore dei dati archiviati non ancora disponibile per questi due tipi di report.</span><span class="sxs-lookup"><span data-stu-id="80be7-187">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="80be7-p122">Quando si fa clic su **Avanti**, viene visualizzata una pagina di riepilogo in cui sono elencate le opzioni di filtro che è stato selezionato, un titolo univoco (modificabile) per il report e l'indirizzo di posta elettronica che riceve la notifica al termine della traccia dei messaggi (anche modificabile, e deve essere in uno dei domini accettati dell'organizzazione). Fare clic su **report di preparazione** per inviare la traccia dei messaggi. Nell'oggetto principale della pagina **traccia dei messaggi** è possibile visualizzare lo stato del report nella sezione **report Downloadable** .</span><span class="sxs-lookup"><span data-stu-id="80be7-p122">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains). Click **Prepare report** to submit the message trace. On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="80be7-191">Per ulteriori informazioni sulle informazioni restituite nei diversi tipi di report, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="80be7-191">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="80be7-192">Risultati di traccia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="80be7-192">Message trace results</span></span>

<span data-ttu-id="80be7-p123">I diversi tipi di report restituiscano diversi livelli di informazioni. Le informazioni disponibili in diversi report sono descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="80be7-p123">The different report types return different levels of information. The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="80be7-195">Output del report di riepilogo</span><span class="sxs-lookup"><span data-stu-id="80be7-195">Summary report output</span></span>

<span data-ttu-id="80be7-196">Dopo aver eseguito la traccia dei messaggi, verranno elencati i risultati vengono ordinati decrescente data/ora (primo più recente).</span><span class="sxs-lookup"><span data-stu-id="80be7-196">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![Risultati dei report di riepilogo per traccia dei messaggi in & la sicurezza centro conformità](media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="80be7-198">Un rapporto di riepilogo contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80be7-198">The summary report contains the following information:</span></span>

- <span data-ttu-id="80be7-199">**Data**: data e ora in cui il messaggio è stato ricevuto dal servizio, utilizzando il fuso orario UTC configurato.</span><span class="sxs-lookup"><span data-stu-id="80be7-199">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="80be7-200">**Mittente**: l'indirizzo di posta elettronica del mittente (*alias*@*dominio*).</span><span class="sxs-lookup"><span data-stu-id="80be7-200">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="80be7-p124">**Destinatario**: l'indirizzo di posta elettronica del destinatario o destinatari. Per un messaggio inviato a più destinatari, non esiste una riga per ogni destinatario. Se il destinatario è un gruppo di distribuzione, gruppo di distribuzione dinamico o gruppo di protezione abilitati alla posta elettronica, il gruppo è il primo destinatario e quindi ogni membro del gruppo è su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="80be7-p124">**Recipient**: The email address of the recipient or recipients. For a message sent to multiple recipients, there's one line per recipient. If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="80be7-204">**Oggetto**: I primi 256 caratteri del messaggio **soggetto:** campo.</span><span class="sxs-lookup"><span data-stu-id="80be7-204">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="80be7-205">**Stato**: questi valori sono descritti nella sezione [stato di recapito](#delivery-status) .</span><span class="sxs-lookup"><span data-stu-id="80be7-205">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="80be7-p125">Per impostazione predefinita, i primi 250 risultati vengono caricati e immediatamente disponibili. Quando scorrere verso il basso, non esiste una pausa leggera in quanto il batch successivo di risultati vengono caricati. Invece di scorrimento, è possibile scegliere di **caricare tutti** per caricare tutti i risultati fino a un massimo di 10.000.</span><span class="sxs-lookup"><span data-stu-id="80be7-p125">By default, the first 250 results are loaded and readily available. When you scroll down, there's a slight pause as the next batch of results are loaded. Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="80be7-209">È possibile fare clic sulle intestazioni di colonna per ordinare i risultati in base ai valori di colonna in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="80be7-209">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="80be7-210">È possibile fare clic su **risultati filtrati** per filtrare i risultati in base a uno o più colonne.</span><span class="sxs-lookup"><span data-stu-id="80be7-210">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="80be7-211">È possibile esportare i risultati dopo che sono state selezionate una o più righe facendo clic su **Esporta risultati** e quindi selezionare **Esporta tutti i risultati**, **esportazione caricato i risultati**o **esportazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="80be7-211">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="80be7-212">Trovare i record correlati per questo messaggio</span><span class="sxs-lookup"><span data-stu-id="80be7-212">Find related records for this message</span></span>

<span data-ttu-id="80be7-p126">Record di messaggi correlati sono record che condivisi lo stesso ID di messaggio. Si tenga presente che anche un singolo messaggio inviato tra due persone può essere generati più record. Aumenta il numero di record quando il messaggio viene influenzato da espansione dei gruppi di distribuzione, inoltro, regole del flusso di posta elettronica (noto anche come regole di trasporto) e così via.</span><span class="sxs-lookup"><span data-stu-id="80be7-p126">Related message records are records that shared the same Message ID. Remember, even a single message sent between two people can generate multiple records. The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="80be7-216">Dopo aver selezionato la casella di controllo della riga, è possibile trovare i record correlati per il messaggio fare clic sul pulsante **Trova correlati** che viene visualizzata o selezionando **altre opzioni** ![più](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **trovare i record correlati per questo messaggio**).</span><span class="sxs-lookup"><span data-stu-id="80be7-216">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="80be7-217">Per ulteriori informazioni sull'ID del messaggio, vedere la sezione ID messaggio più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="80be7-217">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="80be7-218">Dettagli traccia messaggio</span><span class="sxs-lookup"><span data-stu-id="80be7-218">Message trace details</span></span>

<span data-ttu-id="80be7-219">Nell'output del rapporto di riepilogo, è possibile visualizzare informazioni dettagliate su un messaggio utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80be7-219">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="80be7-220">Selezionare la riga (fare clic in qualsiasi punto nella riga ad eccezione della casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="80be7-220">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="80be7-221">Selezionare la casella di controllo della riga e fare clic su **altre opzioni** ![più](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Visualizza dettagli messaggio**.</span><span class="sxs-lookup"><span data-stu-id="80be7-221">Select the row's check box and click **More options** ![More](media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![Dettagli dopo fare doppio clic su una riga nei risultati della traccia dei messaggi rapporto riepilogativo in & la sicurezza centro conformità](media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="80be7-223">I dettagli della traccia messaggio contengono le seguenti informazioni aggiuntive che non sono presente in un rapporto di riepilogo:</span><span class="sxs-lookup"><span data-stu-id="80be7-223">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="80be7-p127">**Gli eventi di messaggio**: in questa sezione contiene le classificazioni che consentono di classificare le azioni eseguite sui messaggi al servizio. Alcuni degli eventi di più interessanti che possono verificarsi sono:</span><span class="sxs-lookup"><span data-stu-id="80be7-p127">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages. Some of the more interesting events that you might encounter are:</span></span>

   - <span data-ttu-id="80be7-226">**Ricezione**: il messaggio è stato ricevuto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="80be7-226">**Receive**: The message was received by the service.</span></span>

   - <span data-ttu-id="80be7-227">**Inviare**: il messaggio è stato inviato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="80be7-227">**Send**: The message was sent by the service.</span></span>

   - <span data-ttu-id="80be7-228">**Errore**: il messaggio non è stato possibile recapitare.</span><span class="sxs-lookup"><span data-stu-id="80be7-228">**Fail**: The message failed to be delivered.</span></span>

   - <span data-ttu-id="80be7-229">**Fornire**: il messaggio è stato recapitato a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="80be7-229">**Deliver**: The message was delivered to a mailbox.</span></span>

   - <span data-ttu-id="80be7-230">**Espandi**: il messaggio è stato inviato a un gruppo di distribuzione che è stato esteso.</span><span class="sxs-lookup"><span data-stu-id="80be7-230">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

   - <span data-ttu-id="80be7-231">**Trasferire**: destinatari sono stati spostati su un messaggio moltiplicato in seguito la conversione del contenuto, limitazioni dei destinatari del messaggio o ad agenti.</span><span class="sxs-lookup"><span data-stu-id="80be7-231">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

   - <span data-ttu-id="80be7-232">**Defer**: il recapito del messaggio è stato rimandato e potrebbe essere effettuato un altro tentativo più avanti.</span><span class="sxs-lookup"><span data-stu-id="80be7-232">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

   - <span data-ttu-id="80be7-p128">**Risolto**: il messaggio è stato reindirizzato a un nuovo indirizzo del destinatario basato su una ricerca Active Directory. In questo caso, l'indirizzo del destinatario originale è elencato in una riga separata nella traccia dei messaggi con lo stato di recapito finale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-p128">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up. When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

   <span data-ttu-id="80be7-235">Si noti che anche un messaggio se viene recapitato con successo genererà più voci relative agli **eventi** di traccia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="80be7-235">Note that even an uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

- <span data-ttu-id="80be7-236">**Ulteriori informazioni**: in questa sezione sono i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="80be7-236">**More information**: This section contains the following details:</span></span>

   - <span data-ttu-id="80be7-p129">**ID messaggio**: questo valore è descritto nella sezione [ID messaggio](#message-id) più indietro in questo argomento. Ad esempio `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="80be7-p129">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

   - <span data-ttu-id="80be7-239">**Dimensione messaggio**</span><span class="sxs-lookup"><span data-stu-id="80be7-239">**Message size**</span></span>

   - <span data-ttu-id="80be7-p130">**Da IP**: l'indirizzo IP del computer che ha inviato il messaggio. Per i messaggi in uscita inviati da Exchange Online, questo valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="80be7-p130">**From IP**: The IP address of the computer that sent the message. For outbound messages sent from Exchange Online, this value is blank.</span></span>

   - <span data-ttu-id="80be7-p131">**IP a**: indirizzo IP o gli indirizzi dove il tentativo del servizio di recapitare il messaggio. Se il messaggio ha più destinatari, queste vengono visualizzate. Per i messaggi in ingresso inviati a Exchange Online, questo valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="80be7-p131">**To IP**: The IP address or addresses where the service attempted to deliver the message. If the message has multiple recipients, these are displayed. For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="80be7-245">Rapporti di riepilogo avanzate</span><span class="sxs-lookup"><span data-stu-id="80be7-245">Enhanced summary reports</span></span>

<span data-ttu-id="80be7-p132">Disponibili rapporti di riepilogo avanzata (completate) sono disponibili nella sezione **report Downloadable** alla traccia dei messaggi di inizio. Le informazioni seguenti sono disponibili nel rapporto:</span><span class="sxs-lookup"><span data-stu-id="80be7-p132">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace. The following information is available in the report:</span></span>

- <span data-ttu-id="80be7-248">**origin_timestamp**<sup>\*</sup>: data e ora quando il messaggio è stata inizialmente ricevuto dal servizio, utilizzando il fuso orario UTC configurato.</span><span class="sxs-lookup"><span data-stu-id="80be7-248">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="80be7-249">**sender_address**: indirizzo di posta elettronica del mittente (*alias*@*dominio*).</span><span class="sxs-lookup"><span data-stu-id="80be7-249">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="80be7-p133">**Recipient_status**: lo stato di recapito del messaggio al destinatario. Se il messaggio è stato inviato a più destinatari, verranno visualizzati tutti i destinatari e allo stato corrispondente per ognuno, nel formato: \< *indirizzo di posta elettronica*\>##\<*stato*\>. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="80be7-p133">**Recipient_status**: The status of the delivery of the message to the recipient. If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>. For example:</span></span>

   - <span data-ttu-id="80be7-253">**##Receive, invia** indica che il messaggio è stato ricevuto dal servizio ed è stato inviato alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="80be7-253">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

   - <span data-ttu-id="80be7-254">**Esito negativo ##Receive,** indica che il messaggio è stato ricevuto dal servizio, ma recapito alla destinazione prevista non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="80be7-254">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

   - <span data-ttu-id="80be7-255">**Fornire ##Receive,** indica che il messaggio è stato ricevuto dal servizio ed è stato recapitato alla cassetta postale del destinatario.</span><span class="sxs-lookup"><span data-stu-id="80be7-255">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="80be7-256">**message_subject**: I primi 256 caratteri del campo **oggetto** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-256">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="80be7-257">**total_bytes**: le dimensioni del messaggio in byte, inclusi gli allegati.</span><span class="sxs-lookup"><span data-stu-id="80be7-257">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="80be7-p134">**message_id**: questo valore è descritto nella sezione [ID messaggio](#message-id) più indietro in questo argomento. Ad esempio `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span><span class="sxs-lookup"><span data-stu-id="80be7-p134">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic. For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="80be7-p135">**network_message_id**: un valore di ID univoci messaggi che vengono mantenute in tutte le copie dei messaggi che possono essere create a causa di espansione dei gruppi di distribuzione o la moltiplicazione. È un valore di esempio `1341ac7b13fb42ab4d4408cf7f55890f`.</span><span class="sxs-lookup"><span data-stu-id="80be7-p135">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion. An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="80be7-262">**original_client_ip**: l'indirizzo IP del client del mittente.</span><span class="sxs-lookup"><span data-stu-id="80be7-262">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="80be7-263">**Direzionalità**: indica che il messaggio è stato inviato all'interno (1) dell'organizzazione o se è stato inviato in uscita (2) dalla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80be7-263">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="80be7-p136">**connector_id**: il nome del connettore di origine o destinazione. Per ulteriori informazioni sui connettori in Exchange Online, vedere [configurare il flusso di posta utilizzando i connettori in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="80be7-p136">**connector_id**: The name of the source or destination connector. For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="80be7-266">**delivery_priority**<sup>\*</sup>: se è stato inviato il messaggio con priorità **alta**, **Low**o **Normal** .</span><span class="sxs-lookup"><span data-stu-id="80be7-266">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="80be7-267"><sup>\*</sup>Queste proprietà sono disponibili solo nei rapporti di riepilogo avanzata.</span><span class="sxs-lookup"><span data-stu-id="80be7-267"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="80be7-268">Report estesa</span><span class="sxs-lookup"><span data-stu-id="80be7-268">Extended reports</span></span>

<span data-ttu-id="80be7-p137">Report estesa (completate) disponibili sono disponibili nella sezione **report Downloadable** all'inizio della traccia dei messaggi. Quasi tutte le informazioni da un rapporto di riepilogo avanzata è disponibile in un report estesa (ad eccezione dei **origin_timestamp** e **delivery_priority**). Sono disponibile in un report Extended solo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80be7-p137">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace. Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**). The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="80be7-272">**client_ip**: l'indirizzo IP del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-272">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="80be7-273">**client_hostname**: il nome host o il nome di dominio completo del server di posta elettronica o del client di messaggistica che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-273">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="80be7-274">**server_ip**: l'indirizzo IP del server di origine o destinazione.</span><span class="sxs-lookup"><span data-stu-id="80be7-274">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="80be7-275">**server_hostname**: il nome host o il nome di dominio completo del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="80be7-275">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="80be7-p138">**source_context**: informazioni Extra associate al campo **origine** . Per esempio:</span><span class="sxs-lookup"><span data-stu-id="80be7-p138">**source_context**: Extra information associated with the **source** field. For example:</span></span>

   - `Protocol Filter Agent`

   - `3489061114359050000`

- <span data-ttu-id="80be7-p139">**origine**: componente di Exchange Online è responsabile dell'evento. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="80be7-p139">**source**: The Exchange Online component that's responsible for the event. For example:</span></span>

   - `AGENT`

   - `MAILBOXRULE`

   - `SMTP`

- <span data-ttu-id="80be7-280">**event_id**: questi corrispondono ai valori illustrati nella sezione [individuare i record correlati per questo messaggio di](#find-related-records-for-this-message) **evento messaggio** .</span><span class="sxs-lookup"><span data-stu-id="80be7-280">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="80be7-281">**internal_message_id**: un identificatore di messaggio che viene assegnato dal server di Exchange Online che sta elaborando il messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-281">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="80be7-p140">**recipient_address**: gli indirizzi di posta elettronica dei destinatari del messaggio. Più indirizzi di posta elettronica sono separati da virgola (;).</span><span class="sxs-lookup"><span data-stu-id="80be7-p140">**recipient_address**: The email addresses of the message's recipients. Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="80be7-284">**recipient_count**: il numero totale di destinatari del messaggio.</span><span class="sxs-lookup"><span data-stu-id="80be7-284">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="80be7-285">**related_recipient_address**: utilizzare in combinazione con `EXPAND`, `REDIRECT`, e `RESOLVE` indirizzi associati a del messaggio di posta elettronica degli eventi per visualizzare altri destinatari.</span><span class="sxs-lookup"><span data-stu-id="80be7-285">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="80be7-p141">**Guida di riferimento**: questo campo contiene informazioni aggiuntive per specifici tipi di eventi. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="80be7-p141">**reference**: This field contains additional information for specific types of events. For example:</span></span>

   - <span data-ttu-id="80be7-p142">**DSN**: contiene il collegamento al report, ovvero il valore **message_id** della notifica stato recapito associato (noto anche come un nome DSN, rapporto di mancato recapito, rapporti di mancato recapito o messaggio di rimbalzo) se un nome DSN viene generato dopo l'evento. Se si tratta di un messaggio DSN, questo campo contiene il valore **message_id** del messaggio originale è stato generato il DSN per.</span><span class="sxs-lookup"><span data-stu-id="80be7-p142">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event. If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

   - <span data-ttu-id="80be7-290">**ESPANDI**: contiene il valore **related_recipient_address** di messaggi correlati.</span><span class="sxs-lookup"><span data-stu-id="80be7-290">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

   - <span data-ttu-id="80be7-291">**Ricezione**: può contenere il valore **message_id** del messaggio correlato se il messaggio è stato generato da altri processi (ad esempio le regole posta in arrivo).</span><span class="sxs-lookup"><span data-stu-id="80be7-291">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

   - <span data-ttu-id="80be7-292">**Inviare**: contiene il valore **internal_message_id** dei messaggi DSN.</span><span class="sxs-lookup"><span data-stu-id="80be7-292">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

   - <span data-ttu-id="80be7-293">**Trasferire**: contiene il valore **internal_message_id** del messaggio viene viene instradato (ad esempio, per la conversione del contenuto, limitazioni dei destinatari del messaggio o ad agenti).</span><span class="sxs-lookup"><span data-stu-id="80be7-293">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

   - <span data-ttu-id="80be7-294">**MAILBOXRULE**: contiene il valore **internal_message_id** del messaggio in ingresso che ha causato la regola di posta in arrivo generare il messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="80be7-294">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

   <span data-ttu-id="80be7-295">Per tutti gli altri tipi di evento, questo campo in genere è vuoto.</span><span class="sxs-lookup"><span data-stu-id="80be7-295">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="80be7-p143">**return_path**: l'indirizzo di posta elettronica mittente specificato dal comando **MAIL FROM** che ha inviato il messaggio. Sebbene questo campo non è vuoto, il valore dell'indirizzo mittente null rappresentato come può contenere `<>`.</span><span class="sxs-lookup"><span data-stu-id="80be7-p143">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message. Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="80be7-p144">**message_info**: informazioni aggiuntive relative al messaggio. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="80be7-p144">**message_info**: Additional information about the message. For example:</span></span>

   - <span data-ttu-id="80be7-p145">Il messaggio origine data / ora in formato UTC per `DELIVER` e `SEND` eventi. Data-ora di origine è l'ora in cui il messaggio immessa innanzitutto l'organizzazione Exchange Online. La data e ora UTC è rappresentata nel formato di data / ora ISO8601: `yyyy-mm-ddThh:mm:ss.fffZ`, dove `yyyy` = anno, `mm` = mese, `dd` = giorno, `T` indica l'inizio del componente ora `hh` = ore, `mm` = minuti, `ss` = secondo, `fff` = frazioni di secondo, e `Z` indica `Zulu`, ovvero un altro modo per indicare l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="80be7-p145">The message origination date-time in UTC for `DELIVER` and `SEND` events. The origination date-time is the time when the message first entered the Exchange Online organization. The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

   - <span data-ttu-id="80be7-p146">Errori di autenticazione. Ad esempio, potrebbe essere visualizzato il valore `11a` e il tipo di autenticazione utilizzato quando si è verificato l'errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="80be7-p146">Authentication errors. For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="80be7-305">**tenant_id**: un valore GUID che rappresenta l'organizzazione Exchange Online (ad esempio `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span><span class="sxs-lookup"><span data-stu-id="80be7-305">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="80be7-306">**original_server_ip**: l'indirizzo IP del server originale.</span><span class="sxs-lookup"><span data-stu-id="80be7-306">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="80be7-p147">**custom_data**: contiene i dati relativi ai tipi di evento specifico. Per ulteriori informazioni, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="80be7-p147">**custom_data**: Contains data related to specific event types. For more information, see the following sections.</span></span>

#### <a name="customdata-values"></a><span data-ttu-id="80be7-309">valori custom_data</span><span class="sxs-lookup"><span data-stu-id="80be7-309">custom_data values</span></span>

<span data-ttu-id="80be7-p148">Il campo **custom_data** per un `AGENTINFO` evento viene utilizzato da un'ampia gamma di agenti di Exchange Online per registrare i dati di elaborazione dei messaggi. Nelle sezioni seguenti vengono descritte alcune degli agenti più interessanti.</span><span class="sxs-lookup"><span data-stu-id="80be7-p148">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details. Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="80be7-312">Agente filtro da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="80be7-312">Spam filter agent</span></span>

<span data-ttu-id="80be7-p149">Un valore **custom_data** che inizia con `S:SFA` è dall'agente filtro posta indesiderata. Nella tabella seguente sono descritti i dettagli principali:</span><span class="sxs-lookup"><span data-stu-id="80be7-p149">A **custom_data** value that starts with `S:SFA` is from the spam filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="80be7-315">**Valore**</span><span class="sxs-lookup"><span data-stu-id="80be7-315">**Value**</span></span>|<span data-ttu-id="80be7-316">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="80be7-316">**Description**</span></span>|
|:-----|:-----|
|`SFV=NSPM`|<span data-ttu-id="80be7-317">Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.</span><span class="sxs-lookup"><span data-stu-id="80be7-317">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="80be7-318">Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.</span><span class="sxs-lookup"><span data-stu-id="80be7-318">The message was marked as spam by the content filter.</span></span>|
|`SFV=BLK`|<span data-ttu-id="80be7-319">Le regole del filtro sono state ignorate e il messaggio è stato bloccato perché è stato originato da un mittente bloccato.</span><span class="sxs-lookup"><span data-stu-id="80be7-319">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="80be7-p150">Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alle regole di trasporto, che lo contrassegnano automaticamente come indesiderato e che ignorano tutte le regole del filtro aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="80be7-p150">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="80be7-322">Per ulteriori informazioni sui valori SCL differenti e sul loro aspetto, vedere [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span><span class="sxs-lookup"><span data-stu-id="80be7-322">For more information about the different SCL values and what they mean, see [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`PCL=<number>`|<span data-ttu-id="80be7-p151">Il valore di livello di probabilità di Phishing (PCL) del messaggio. Questi possono essere interpretati esattamente come il valore SCL valori documentati nei [livelli di probabilità di posta indesiderata](https://technet.microsoft.com/library/jj200686.aspx).</span><span class="sxs-lookup"><span data-stu-id="80be7-p151">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](https://technet.microsoft.com/library/jj200686.aspx).</span></span>|
|`DI=SB`|<span data-ttu-id="80be7-325">Il mittente del messaggio è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="80be7-325">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="80be7-326">Il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="80be7-326">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="80be7-327">Il messaggio è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="80be7-327">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="80be7-328">Il messaggio è stato inviato nella cartella posta indesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="80be7-328">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="80be7-p152">Il messaggio è stato instradato tramite il pool recapito ad alto rischio. Per ulteriori informazioni, vedere [pool di recapito ad alto rischio per i messaggi in uscita](https://technet.microsoft.com/library/jj200746.aspx).</span><span class="sxs-lookup"><span data-stu-id="80be7-p152">The message was routed through the higher risk delivery pool. For more information, see [High-risk delivery pool for outbound messages](https://technet.microsoft.com/library/jj200746.aspx).</span></span>|
|`DI=SO`|<span data-ttu-id="80be7-331">Il messaggio è stato instradato tramite un pool di recapito ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="80be7-331">The message was routed through the normal outbound delivery pool.</span></span>|
|<span data-ttu-id="80be7-332">' SFS = [un]</span><span class="sxs-lookup"><span data-stu-id="80be7-332">\`SFS=[a]</span></span>|<span data-ttu-id="80be7-333">SFS = [b]'</span><span class="sxs-lookup"><span data-stu-id="80be7-333">SFS=[b]\`</span></span>|<span data-ttu-id="80be7-334">Indica una corrispondenza tra le regole relative alla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="80be7-334">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="80be7-335">Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.</span><span class="sxs-lookup"><span data-stu-id="80be7-335">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="80be7-336">La stringa HELO o EHLO del server in connessione posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="80be7-336">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="80be7-337">Il record PTR dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.</span><span class="sxs-lookup"><span data-stu-id="80be7-337">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|

<span data-ttu-id="80be7-338">Un valore **custom_data** di esempio per un messaggio viene filtrato per posta indesiderata simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="80be7-338">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="80be7-339">Agente di filtro malware</span><span class="sxs-lookup"><span data-stu-id="80be7-339">Malware filter agent</span></span>

<span data-ttu-id="80be7-p153">Un valore **custom_data** che inizia con `S:AMA` è dall'agente filtro malware. Nella tabella seguente sono descritti i dettagli principali:</span><span class="sxs-lookup"><span data-stu-id="80be7-p153">A **custom_data** value that starts with `S:AMA` is from the malware filter agent. The key details are described in the following table:</span></span>

|<span data-ttu-id="80be7-342">**Valore**</span><span class="sxs-lookup"><span data-stu-id="80be7-342">**Value**</span></span>|<span data-ttu-id="80be7-343">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="80be7-343">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80be7-344">' AMA = SOMMA</span><span class="sxs-lookup"><span data-stu-id="80be7-344">\`AMA=SUM</span></span>|<span data-ttu-id="80be7-345">v = 1</span><span class="sxs-lookup"><span data-stu-id="80be7-345">v=1</span></span>|<span data-ttu-id="80be7-346">` or `AMA = EV</span><span class="sxs-lookup"><span data-stu-id="80be7-346">` or `AMA=EV</span></span>|<span data-ttu-id="80be7-347">v = 1'</span><span class="sxs-lookup"><span data-stu-id="80be7-347">v=1\`</span></span>|<span data-ttu-id="80be7-p154">Il messaggio è stato determinato come contenente malware. `SUM` indica malware è stato rilevato da un numero qualsiasi di moduli. `EV` indica il malware rilevato da un determinato modulo. Quando viene rilevato malware da un motore che si generano le azioni successive.</span><span class="sxs-lookup"><span data-stu-id="80be7-p154">The message was determined to contain malware. `SUM` indicates the malware could've been detected by any number of engines. `EV` indicates the malware was detected by a specific engine. When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="80be7-352">Il messaggio è stato sostituito.</span><span class="sxs-lookup"><span data-stu-id="80be7-352">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="80be7-353">Il messaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="80be7-353">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="80be7-354">Il messaggio è stato rinviato.</span><span class="sxs-lookup"><span data-stu-id="80be7-354">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="80be7-355">Il messaggio è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="80be7-355">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="80be7-356">Il messaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="80be7-356">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="80be7-357">Il messaggio è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="80be7-357">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="80be7-358">Il messaggio è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="80be7-358">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="80be7-359">Il messaggio è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="80be7-359">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="80be7-360">Il messaggio è stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="80be7-360">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="80be7-361">Il nome del malware rilevato.</span><span class="sxs-lookup"><span data-stu-id="80be7-361">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="80be7-362">Il nome del file che contiene malware.</span><span class="sxs-lookup"><span data-stu-id="80be7-362">The name of the file that contained the malware.</span></span>|

<span data-ttu-id="80be7-363">Un valore **custom_data** di esempio per un messaggio che contiene malware simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="80be7-363">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="80be7-364">Agente della regola di trasporto</span><span class="sxs-lookup"><span data-stu-id="80be7-364">Transport rule agent</span></span>

<span data-ttu-id="80be7-p155">Un valore **custom_data** che inizia con`S:TRA` è dall'agente regole di trasporto per le regole del flusso di posta elettronica (noto anche come regole di trasporto). Nella tabella seguente sono descritti i dettagli principali:</span><span class="sxs-lookup"><span data-stu-id="80be7-p155">A **custom_data** value that starts with`S:TRA` is from the transport rule agent for mail flow rules (also known as transport rules). The key details are described in the following table:</span></span>

|<span data-ttu-id="80be7-367">**Valore**</span><span class="sxs-lookup"><span data-stu-id="80be7-367">**Value**</span></span>|<span data-ttu-id="80be7-368">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="80be7-368">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80be7-369">' ETR</span><span class="sxs-lookup"><span data-stu-id="80be7-369">\`ETR</span></span>|<span data-ttu-id="80be7-370">ruleId =<guid>\`</span><span class="sxs-lookup"><span data-stu-id="80be7-370">ruleId=<guid>\`</span></span>|<span data-ttu-id="80be7-371">L'ID regola corrispondente.</span><span class="sxs-lookup"><span data-stu-id="80be7-371">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="80be7-372">Data e ora in formato UTC quando si è verificata la corrispondenza della regola.</span><span class="sxs-lookup"><span data-stu-id="80be7-372">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="80be7-p156">L'azione che sono stato applicato. Per un elenco delle azioni disponibili, vedere [Mail flow azioni delle regole di Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span><span class="sxs-lookup"><span data-stu-id="80be7-p156">The action that was applied. For a list of available actions, see [Mail flow rule actions in Exchange Online](https://technet.microsoft.com/library/jj919237.aspx).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="80be7-p157">La modalità della regola. I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="80be7-p157">The mode of the rule. Valid values are: </span></span><br/><span data-ttu-id="80be7-377">• **Applica**: tutte le azioni della regola verranno applicate.</span><span class="sxs-lookup"><span data-stu-id="80be7-377">• **Enforce**: All actions on the rule will be enforced.</span></span> <br/><span data-ttu-id="80be7-378">• **Test con suggerimenti criteri:**: le azioni del suggerimento criteri qualsiasi verranno inviate, ma non verranno applicate altre azioni su.</span><span class="sxs-lookup"><span data-stu-id="80be7-378">• **Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span> <br/><span data-ttu-id="80be7-379">• **Verifica senza i suggerimenti criteri**: le azioni verranno elencate in un file di registro, ma i mittenti non riceveranno alcuna notifica e azioni non verranno applicate in.</span><span class="sxs-lookup"><span data-stu-id="80be7-379">• **Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span>|

<span data-ttu-id="80be7-380">Un valore **custom_data** di esempio per un messaggi che soddisfa le condizioni di una regola del flusso di posta elettronica è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="80be7-380">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
