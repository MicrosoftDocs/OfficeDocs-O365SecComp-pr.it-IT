---
title: Panoramica di eDiscovery avanzate (Preview) in Microsoft 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritta la nuova versione di eDiscovery avanzate (Preview) in Microsoft 365.
ms.openlocfilehash: aed4739db02ffda83319ada5b1c5fdf20426a1fa
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607889"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a>Panoramica di eDiscovery avanzate (Preview) in Microsoft 365

Microsoft ha appena rilasciato una versione di anteprima dello strumento eDiscovery avanzate aggiornati che si basa sulle funzionalità eDiscovery esistente in Office 365. Questa versione di anteprima, denominata *eDiscovery avanzate (anteprima)*, offre un flusso di lavoro end-to-end per mantenere, raccogliere, esaminare, analizzare ed esportare il contenuto che risponde a indagini interni ed esterni dell'organizzazione. 

## <a name="alignment-with-edrm"></a>Allineamento con EDRM

Il flusso di lavoro predefinito di eDiscovery avanzate (Preview) viene allineato con il processo di eDiscovery descritto dal modello di riferimento Electronic Discovery (EDRM). 

![Il modello di riferimento di Electronic Discovery (EDRM)](../media/EDRMv1.png)

(Origine dell'immagine per edrm.net. Immagine di origine è stata effettuata disponibile con Creative comuni Attribution 3.0 licenza Unported.)

A un livello superiore, eDiscovery modalità avanzata Ecco (Preview) supporta il flusso di lavoro EDRM:

- **Identificazione** - dopo aver identificato potenziali persone di interesse indagini, è possibile aggiungerli come depositari (denominati anche *depositari dati*, poiché potrebbe dispongono delle informazioni rilevanti per le indagini) a un avanzata caso di eDiscovery (Preview). Dopo che gli utenti vengono aggiunti come depositari, è facile da conservare, raccogliere e controllare i documenti depositaria.

- **Conservazione** - per conservare e proteggere i dati rilevanti per un indagini avanzate eDiscovery (Preview) è che possibile posizionare una conservazione a fini giudiziari in origini dati che sono associate depositari in caso. È inoltre possibile inserire i dati non detentive in attesa. Inoltre, eDiscovery avanzate (Preview) ha un flusso di lavoro incorporati communications in modo che è possibile inviare una conservazione a fini giudiziari notifiche ai depositari e tenere traccia delle loro riconoscimenti.

- **Insieme** - dopo aver identificato (e mantenute) le origini dati rilevanti per le indagini, è possibile utilizzare lo strumento di ricerca incorporate in ricerca eDiscovery avanzate (Preview) e Raccogli dati in tempo reale dalle origini dati detentive (e non detentive origini dati, se applicabile) che possono essere pertinenti per il case.

- **Elaborazione** - dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo è processo di analisi e un'ulteriore verifica. In eDiscovery avanzate (anteprima), indica che i dati sul posto definito in fase di raccolta vengono copiati nel percorso di archiviazione Azure denominato un *insieme di lavoro*, che consente di ottenere una visualizzazione statica dei dati maiuscole. 
 
- Impostare **la revisione** - dopo l'aggiunta di dati per un utilizzo, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per  
 
- **Analisi** - avanzate eDiscovery (Preview) sono disponibili strumenti analitica integrata che consente di riforma dati dal set di lavoro che vengono considerate non rilevanti per le indagini. Oltre a ridurre il volume di dati pertinenti, eDiscovery anticipo (Preview) consente di salvare i costi di revisione legale grazie alla possibilità di organizzare il contenuto per semplificare il processo di revisione e più efficiente.

- **Produzione** e **presentazione** , una volta pronti, è possibile esportare documenti da un gruppo di lavoro per la revisione legale. È possibile esportare documenti nel formato nativo o in un formato EDRM specificato in modo che possono essere importati nelle applicazioni di terze parti revisione.

## <a name="advanced-ediscovery-preview-workflow"></a>Flusso di lavoro eDiscovery avanzate (Preview)

Nelle sezioni seguenti viene descritto ogni passaggio del flusso di lavoro predefiniti di eDiscovery avanzate (Preview). La schermata seguente mostra la scheda **home page** di un caso denominato *2019002 responsabilità del prodotto*. Si noti che il flusso di lavoro nella parte superiore della pagina vengono eseguiti nella sequenza per allineare il processo EDRM. 

Per ulteriori informazioni sul flusso di lavoro end-to-end di eDiscovery avanzate (anteprima), vedere questo [Meccanismi Microsoft video](https://go.microsoft.com/fwlink/?linkid=2066133). 

![Schede di eDiscovery avanzate (Preview) seguono il flusso di lavoro EDRM](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a>Gestione depositari

Utilizzare la scheda **depositari** per aggiungere e gestire le persone che è stato identificato come persone di interesse nel caso. Quando si aggiungono depositari, è possibile eseguire le azioni relative depositaria ad esempio l'aggiunta di una persona come nelle origini dati depositaria, ad esempio la cassetta postale e l'account di OneDrive rapidamente la comunicazione con depositari e le origini dati depositaria per la raccolta di contenuto di ricerca che si applicano a caso. Come avanzamento dei casi, risulta molto semplice aggiungere nuovi depositari o la versione depositari dal caso. Per ulteriori informazioni, vedere [Working with depositari di eDiscovery avanzate (Preview)](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Gestione delle notifiche di conservazione a fini giudiziari

Utilizzare la scheda **comunicazioni** per gestire il processo di comunicazione con depositari nel caso. Un avviso di conservazione a fini giudiziari indica depositari devono essere mantenuti qualsiasi contenuto che può essere pertinente per il case. I team legali devono essere in grado di verificare che gli avvisi sono stati ricevuti, leggi e riconosciuti dalla depositari. Il flusso di lavoro di comunicazioni di eDiscovery avanzate (Preview) consente di creare e inviare notifiche iniziali, promemoria, versione avvisi e le misure correttive se depositari non riesce a riconoscere una notifica di attesa. Per ulteriori informazioni, vedere [utilizzo delle comunicazioni di eDiscovery avanzate (Preview)](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Gestione di archiviazione del contenuto

Quando si aggiunge un depositaria a un caso, è possibile inserire un'esenzione detentive dati. Utilizzare la scheda **archiviazione** per la gestione dell'esenzione creato quando si aggiungono depositari e gestione legale aggiuntive contiene associata al caso; ad esempio, si possono identificare e mettere un'esenzione in origini dati non detentive. È possibile modificare qualsiasi conservazione nel caso e rendere una conservazione basata su query in modo che solo il contenuto corrispondente alla query viene messa in attesa; ad esempio, è possibile aggiungere un intervallo di date per la conservazione in modo che solo il contenuto che è stato creato all'interno di una data specifica intervallo mantenute. È inoltre ottenere le statistiche sul contenuto che è in attesa, rimuovere la conservazione dopo quando non è più rilevante per il caso o eliminarlo. Per ulteriori informazioni, vedere [gestione delle esenzioni in eDiscovery avanzate (Preview)](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indicizzazione di dati depositaria

Quando si aggiunge un depositaria e le origini dati detentive corrispondente a un caso, qualsiasi elemento parzialmente indicizzato da un'origine dati depositaria è reindicizzazione (per processo denominato *indicizzazione avanzata*). In questo modo detentive contenuto, ad esempio immagini, tipi di file non supportati e altro contenuto potenzialmente non indicizzato per le ricerche completamente durante l'esecuzione di ricerche per raccogliere i dati rilevanti al caso. Utilizzare la scheda **di elaborazione** per monitorare lo stato di indicizzazione avanzate e correzione elaborazione errori (utilizzando un calle processo *correzione errore*). Per ulteriori informazioni, vedere [correzione elaborazione degli errori di eDiscovery avanzate (Preview)](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Raccolta dei dati del caso

Utilizzare la scheda **ricerche** per creare le ricerche per cercare i in loco detentive e origini dati non detentive in Office 365 per il contenuto pertinente al caso. È possibile creare ed eseguire ricerche basate su query (utilizzando le parole chiave e condizioni) per identificare un set i messaggi di posta elettronica e documenti rilevanti per il case e si desidera ampliare la revisione e analizzare nei passaggi successivi del flusso di lavoro di eDiscovery. È possibile creare uno o più ricerche associate al caso. Inoltre, è possibile utilizzare lo strumento di ricerca per visualizzare in anteprima i documenti di esempio e visualizzare le statistiche ricerca possono risultare utili per definire e migliorare i risultati della ricerca. Una volta si è stati soddisfatti che i risultati della ricerca contiene tutti i dati rilevanti per il caso, si aggiungere i risultati della ricerca a un set di lavoro per un ulteriore esame, analisi e se necessario, l'eliminazione selettiva. Per ulteriori informazioni, vedere [la raccolta di dati per un caso di eDiscovery avanzate (Preview)](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzig-case-data"></a>Revisione e analyzig dati maiuscole

Utilizzare la scheda **utilizzo set** o esaminare e analizzare il contenuto raccolti dal sistema live e aggiunto a un gruppo di lavoro. Un *insieme di lavoro* è un insieme statico (in altre parole, una copia non in linea di dat) di dati detentive (e, se applicabile, dati non detentive) raccolti nella fase precedente del flusso di lavoro eDiscovery. Quando si aggiunge i risultati di ricerca a un gruppo di lavoro, viene attivato un processo che consente di estrarre i file dai contenitori, estrae i metadati ed estrae il testo. Una volta completato il processo, il sistema si basa un nuovo indice di tutti i dati raccolti da depositari ed è stata aggiunta al set di lavoro. Dopo aver aggiunto i dati nell'insieme di lavoro, è possibile eseguire query aggiuntive per limitare i dati sui casi, visualizzare i dati sotto forma di testo o nel formato di file nativo e aggiungere note, redigi e contrassegnare i documenti in working set. Inoltre, è possibile eseguire analitica avanzate, ad esempio identificare la duplicazione di documenti, posta elettronica threading e dei temi. Dopo aver facce i dati alle quali è rilevante solo al caso è possibile scaricare i documenti download direttamente o esportarli insieme a qualsiasi tag, le annotazioni e metadati dei file. Per ulteriori informazioni, vedere:

  - [Analisi dei dati casi di eDiscovery avanzate (Preview)](reviewing-data-in-working-set.md)
  - [Analisi dei dati in un working set di eDiscovery avanzate (Preview)](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Esportazione dei dati per la revisione e presentazione

Dopo aver esportato i dati da un gruppo di lavoro, utilizzare la scheda **esportazioni** per gestire un processo di esportazione e scaricare i dati da un gruppo di lavoro. Quando si esporta un working set, i dati caricati in una posizione di archiviazione Azure e quindi sono disponibili per il download in un computer locale. È possibile ottenere la posizione e archiviazione valutare la chiave necessaria per scaricare i dati esportati nella scheda **Esporta** . Per ulteriori informazioni, vedere [esportazione dei dati casi di eDiscovery avanzate (Preview)](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Gestione dei processi

Utilizzare la scheda **processi** per monitorare i processi di lunga durata per operazioni riguardanti il caso che è stato avviato, le ricerche come la reindicizzazione, ricerche ed esportazioni. Ad esempio, è possibile creare una nuova ricerca nella scheda **ricerche** che include un numero elevato di origini dati. Lo stato del processo di ricerca viene visualizzato nella scheda **processi** . Per ulteriori informazioni, vedere [gestione dei processi di eDiscovery avanzate (Preview)](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Configurazione delle impostazioni di maiuscole

Utilizzare la scheda **Impostazioni** per configurare le impostazioni a livello di case. Include l'aggiunta di membri a un caso, parentesi o eliminazione di un caso e la configurazione del comportamento di ricerca e analitica. Per ulteriori informazioni, vedere [configurazione delle impostazioni dei caso di eDiscovery avanzate (Preview)](configuring-case-settings-ediscovery20.md).

