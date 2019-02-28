---
title: Panoramica di Advanced eDiscovery (Preview) in Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritta la nuova versione di Advanced eDiscovery (Preview) in Microsoft 365.
ms.openlocfilehash: 2296f4ee1867cacc90eada9e5f12888a8ea0d242
ms.sourcegitcommit: 13c601ea11ce6a3c71036fdafda059061c6998d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2019
ms.locfileid: "30313152"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a>Panoramica di Advanced eDiscovery (Preview) in Microsoft 365

Microsoft ha appena rilasciato una versione di anteprima dello strumento Advanced eDiscovery aggiornato che si basa sulle funzionalità di eDiscovery esistenti in Office 365. Questa versione di anteprima, denominata *Advanced eDiscovery (Preview)*, offre un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare il contenuto rispondente alle indagini interne ed esterne dell'organizzazione. 

## <a name="alignment-with-edrm"></a>Allineamento con EDRM

Il flusso di lavoro incorporato di Advanced eDiscovery (Preview) è allineato al processo eDiscovery delineato dal modello di riferimento di Electronic Discovery (EDRM). 

![EDRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Fonte di immagini per gentile concessione di edrm.net. L'immagine di origine è stata resa disponibile nella licenza Creative Commons Attribution 3,0 Unported.

A livello elevato, ecco come Advanced eDiscovery (Preview) supporta il flusso di lavoro di EDRM:

- **Identificazione** -dopo aver identificato potenziali persone di interesse in un'indagine, è possibile aggiungerli come depositari (denominati anche *depositari dei dati*, in quanto possono essere in possesso di informazioni rilevanti per l'inchiesta) a un avanzato eDiscovery (anteprima) caso. Dopo che gli utenti vengono aggiunti come depositari, è facile conservare, raccogliere e rivedere i documenti del custode.

- **Preservation** -per preservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery (Preview) consente di inserire una conservazione legale sulle origini dati associate ai depositari in un caso. È inoltre possibile inserire i dati non detentivi in attesa. Inoltre, Advanced eDiscovery (Preview) è dotato di un flusso di lavoro di comunicazione incorporato in modo da poter inviare notifiche di archiviazione legale ai depositari e tenere conto dei loro ringraziamenti.

- **Raccolta** -dopo aver identificato (e conservato) le origini dati rilevanti per l'indagine, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery (Preview) per cercare e raccogliere dati in tempo reale dalle origini dati detentive (e non detentive le origini dati, se applicabile, potrebbero essere rilevanti per il caso.

- **Elaborazione** : dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nell'elaborarla per ulteriori analisi. In Advanced eDiscovery (Preview), questo significa che i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *working set*), in cui viene fornita una visualizzazione statica dei dati del caso. 
 
- **Revisione** -dopo che i dati sono stati aggiunti a un working set, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più pertinente al caso. Inoltre, è possibile annotare e contrassegnare documenti specifici.
 
- **Analysis** -Advanced eDiscovery (Preview) fornisce strumenti di analisi integrata che consentono di eliminare ulteriormente i dati dal working set che si determina non è pertinente per l'indagine. Oltre a ridurre il volume dei dati rilevanti, Advance eDiscovery (Preview) aiuta anche a salvare i costi di revisione legale, consentendo di organizzare il contenuto per rendere più semplice ed efficiente il processo di revisione.

- **Produzione** e **presentazione** -quando si è pronti, è possibile esportare i documenti da un working set per la revisione legale. È possibile esportare documenti nel formato nativo o in un formato specificato per EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.

## <a name="advanced-ediscovery-preview-workflow"></a>Flusso di lavoro avanzato di eDiscovery (anteprima)

Nelle sezioni seguenti vengono descritti i singoli passaggi del flusso di lavoro incorporato in Advanced eDiscovery (Preview). Nella schermata seguente viene illustrata la scheda **Home** di un caso denominato *Product passivity 2019002*. Nota le schede del flusso di lavoro nella parte superiore della pagina vengono sequenziate per essere allineate al processo EDRM. 

Per ulteriori informazioni sul flusso di lavoro end-to-end in Advanced eDiscovery (Preview), vedere this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133). 

![Tabs in Advanced eDiscovery (Preview) seguire il flusso di lavoro di EDRM](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>Gestione dei responsabili

Utilizzare la scheda **depositari** per aggiungere e gestire le persone che sono state identificate come persone di interesse nel caso. Quando si aggiungono depositari, è possibile eseguire rapidamente azioni relative a un custode come la conservazione di un blocco legale su origini dati depositarie, ad esempio la cassetta postale e l'account OneDrive, la comunicazione con i depositari e la ricerca di origini dati depositarie per la raccolta del contenuto. Questo è pertinente per il caso. Quando il caso progredisce, è facile aggiungere nuovi depositari o rilasciarli dal caso. Per ulteriori informazioni, vedere [lavorare con i depositari in Advanced eDiscovery (Preview)](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Gestione delle notifiche di blocco legale

Utilizzare la scheda **comunicazioni** per gestire il processo di comunicazione con i depositari nel caso. Un avviso per la conservazione legale indica ai depositari di conservare qualsiasi contenuto che potrebbe essere pertinente alla causa. I team legali devono essere in grado di tenere conto del fatto che le notifiche sono state ricevute, lette e riconosciute dai depositari. Il flusso di lavoro per le comunicazioni in Advanced eDiscovery (Preview) consente di creare e inviare notifiche iniziali, promemoria, comunicazioni di rilascio e escalation se i depositari non riconoscono una notifica di blocco. Per ulteriori informazioni, vedere [work with Communications in Advanced eDiscovery (Preview)](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Gestione della conservazione dei contenuti

Quando si aggiunge un custode a un caso, si ha la possibilità di applicare un blocco ai dati della custodia. Utilizzare la **** scheda esenzioni per gestire il blocco creato quando si aggiungono i depositari e per gestire ulteriori esenzioni legali associate al caso (ad esempio, è possibile identificare e inserire un'esenzione su origini dati non detentive). È inoltre possibile modificare eventuali esenzioni nel caso e renderla una conservazione basata su query in modo che venga messo in attesa solo il contenuto che corrisponde alla query. Ad esempio, è possibile aggiungere un intervallo di date alla conservazione in modo che solo il contenuto creato all'interno di una data specifica sia stato conservato. È anche possibile ottenere statistiche sul contenuto che è in attesa, rimuovere il blocco dopo che non è più pertinente al caso o eliminarlo. Per ulteriori informazioni, vedere [Manage holds in Advanced eDiscovery (Preview)](managing-holds.md).

## <a name="indexing-custodian-data"></a>InDicizzazione dei dati del custode

Quando si aggiunge un custode e le origini dati di custodia corrispondenti a un caso, qualsiasi elemento parzialmente indicizzato da un'origine dati di un oggetto depositaria viene reindicizzato (tramite un processo denominato *Advanced Indexing*). In questo modo, è possibile eseguire ricerche per raccogliere i dati per il caso in cui vengono eseguiti i contenuti di custodia, quali immagini, tipi di file non supportati e altri contenuti potenzialmente non indicizzati. Utilizzare la scheda **elaborazione** per monitorare lo stato dell'indicizzazione avanzata e correggere gli errori di elaborazione (utilizzando ** un processo denominato correzione degli errori). Per ulteriori informazioni, vedere [correggere gli errori di elaborazione in Advanced eDiscovery (Preview)](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Raccolta dei dati del caso

Utilizzare la scheda **ricerche** per creare ricerche per cercare le origini dati in locale e non detentive in Office 365 per i contenuti rilevanti per il caso. È possibile creare ed eseguire ricerche basate su query (utilizzando parole chiave e condizioni) per identificare un insieme di messaggi di posta elettronica e documenti rilevanti per il caso e che si desidera esaminare e analizzare ulteriormente nei passaggi successivi del flusso di lavoro di eDiscovery. È possibile creare una o più ricerche associate al caso. Inoltre, è possibile utilizzare lo strumento di ricerca per visualizzare in anteprima i documenti di esempio e visualizzare le statistiche di ricerca che possono aiutare a affinare e migliorare i risultati della ricerca. Dopo aver verificato che i risultati della ricerca contengono tutti i dati rilevanti per il caso, è possibile aggiungere i risultati della ricerca a un working set per ulteriori riesami, analisi e, se necessario, eliminazione. Per ulteriori informazioni, vedere [raccolta di dati per un caso in Advanced eDiscovery (Preview)](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Revisione e analisi dei dati del caso

Utilizzare la scheda **working sets** per esaminare e analizzare il contenuto raccolto dal sistema Live e aggiungerlo a un working set. Un *working set* è una raccolta statica di tali dati (in altre parole, una copia offline di dati) dei dati di custodia (e, se applicabile, i dati non detentivi) raccolti nella fase precedente del flusso di lavoro di eDiscovery. Quando si aggiungono i risultati di ricerca a un working set, viene attivato un processo che estrae i file dai contenitori, estrae i metadati ed estrae il testo. Al termine del processo, il sistema genera un nuovo indice di tutti i dati raccolti da depositari e aggiunti al working set. Dopo aver aggiunto i dati al working set, è possibile eseguire query aggiuntive per limitare i dati del caso, visualizzare i dati come testo o nel formato di file nativo e annotare, redigere e contrassegnare i documenti nel working set. È inoltre possibile eseguire analisi avanzate, ad esempio la duplicazione dei documenti, il threading di posta elettronica e i temi. Dopo aver abbattuto i dati solo su ciò che è pertinente per il caso, è possibile scaricare i documenti direttamente o esportarli insieme ai metadati, alle annotazioni e ai tag dei file. Per ulteriori informazioni, vedere:

  - [Esaminare i dati dei casi in Advanced eDiscovery (Preview)](reviewing-data-in-working-set.md)
  - [Analizzare i dati in un working set in Advanced eDiscovery (Preview)](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Esportazione di dati per la revisione e la presentazione

Dopo aver esportato i dati da un working set, **** utilizzare la scheda exports per gestire un processo di esportazione e scaricare i dati da un working set. Quando si esporta un working set, i dati vengono caricati in un percorso di archiviazione di Azure e quindi sono disponibili per essere scaricati in un computer locale. È possibile ottenere la chiave di valutazione percorso e archiviazione necessaria per scaricare i dati esportati nella scheda esPortazioni. **** Per ulteriori informazioni, vedere [Export case data in Advanced eDiscovery (Preview)](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Gestione dei processi

Utilizzare la scheda **processi** per monitorare i processi a esecuzione prolungata per le attività correlate al caso che sono state avviate. Esempi di processi includono quelli relativi alla reindicizzazione, alle ricerche e alle esportazioni. Ad esempio, è possibile creare una nuova ricerca nella scheda **ricerche** che include un numero elevato di origini dati. Lo stato di questo processo di ricerca viene visualizzato nella scheda **processi** . Per ulteriori informazioni, vedere [gestire i processi in Advanced eDiscovery (Preview)](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configurazione delle impostazioni dei casi

Utilizzare la scheda **Impostazioni** per configurare le impostazioni a livello di maiuscole e minuscole. Questo include l'aggiunta di membri a un caso, la chiusura o l'eliminazione di un caso e la configurazione del comportamento di ricerca e analisi. Per ulteriori informazioni, vedere [Configure case Settings in Advanced eDiscovery (Preview)](configuring-case-settings-ediscovery20.md).
