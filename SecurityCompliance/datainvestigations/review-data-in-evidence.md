---
title: Esaminare i dati in evidenza
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
description: ''
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030224"
---
# <a name="review-data-in-evidence"></a>Esaminare i dati in evidenza

**Evidence** è uno snapshot dei risultati della ricerca raccolti. Quando si aggiungono i risultati della ricerca all'evidenza, viene attivato un processo per estrarre file, metadati e testo. Successivamente, il sistema genera un nuovo indice di tutti i dati e aggiunge l' **elemento Evidence**. 

Per eventuali incidenti sensibili al tempo, in questo modo è possibile contenere rapidamente l'ambiente eliminando i dati nei percorsi originali durante l'analisi delle evidenze ricreate in un ambiente in quarantena. Una volta raccolti i dati, è possibile esaminare singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo. Inoltre, è possibile eseguire query per limitare i dati in base a intervallo di tempo, tipi di file, proprietari di dati e molte altre schede di condizione. Utilizzando le schede delle condizioni autore/mittente/destinatario, è possibile esaminare rapidamente gli utenti coinvolti nella fuoriuscita e se sono presenti parti esterne. Per ulteriori informazioni, vedere:

  - [Eseguire una query sui dati in evidenza](evidence-query.md)

Per raggruppare i documenti e ottenere assistenza per la revisione, fare clic su **Gestisci evidenza**. Nel riquadro **analisi** fare clic su **analizza**. Verrà eseguito l'analisi avanzata, ad esempio il rilevamento duplicato, il threading di posta elettronica e l'analizzatore dei temi. Successivamente, è possibile visualizzare i temi generali dei dati e anche organizzare i documenti tramite thread di posta elettronica, duplicati esatti e duplicati quasi per facilitare l'indagine. Per ulteriori informazioni, vedere:

  - [Eseguire analisi per analizzare più velocemente](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a>Visualizzare i documenti in evidenza

L'analisi dei dati (Preview) Visualizza il contenuto tramite diversi visualizzatori ognuno con diversi scopi. È possibile utilizzare i diversi visualizzatori facendo clic su qualsiasi documento in **evidenza**. I visualizzatori attualmente forniti sono:

- Metadati dei file
- Visualizzazione nativa
- Visualizzazione testo
- Visualizzazione anNotazioni
- Visualizzazione convertita

## <a name="file-metadata"></a>Metadati dei file

Questo pannello può essere attivato/disattivato per visualizzare i vari metadati associati al documento. Anche se la griglia dei risultati di ricerca può essere personalizzata per la visualizzazione di metadati specifici, è possibile che lo scorrimento orizzontale possa essere difficoltoso durante la revisione dei dati. Il pannello metadati file consente a un utente di alternare una visualizzazione all'interno del visualizzatore.

![Pannello metadati file
](../media/Reviewimage2.png)

## <a name="native-view"></a>Visualizzazione nativa

Il Visualizzatore nativo Visualizza la visualizzazione più ricca di un documento. Supporta centinaia di tipi di file e ha lo scopo di visualizzare l'esperienza più vera e nativa possibile. Per i file di Microsoft Office, ad esempio, il visualizzatore utilizza Office Online per visualizzare contenuti quali commenti a documenti, formule di Excel, righe/colonne nascoste, note di PowerPoint e così via. Per ulteriori informazioni sui visualizzatori di Office Online, visitare \[il collegamento necessario\]

![Visualizzazione nativa
](../media/Reviewimage3.png)

## <a name="text-view"></a>Visualizzazione testo

Il Visualizzatore di testo consente di visualizzare il testo estratto di un file. Ignora tutte le immagini e la formattazione incorporate, ma sarà una visualizzazione molto perFormante se un utente cerca di comprendere rapidamente il contenuto. La visualizzazione testo include anche altre caratteristiche:

  - Il contatore linea rende più facile fare riferimento a parti specifiche di un documento

  - Evidenziazione hit Search che evidenzierà i termini all'interno del documento e la barra di scorrimento

  - La visualizzazione diff fornisce una visualizzazione di confronto che evidenzia le differenze testuali quando si visualizza vicino a documenti duplicati

![Visualizzazione testo
](../media/Reviewimage4.png)

![Visualizzazione diff
](../media/Reviewimage5.png)

## <a name="annotate-view"></a>Visualizzazione anNotazioni

La visualizzazione anNotazioni fornisce caratteristiche che consentono agli utenti di applicare il markup su un documento durante le indagini, tra cui:

  - Redazioni area: gli utenti possono disegnare una casella del documento per nascondere i contenuti sensibili

  - Matita: gli utenti possono disegnare a mano libera su un documento per portare l'attenzione su determinate parti di un documento.

  - Seleziona annotazioni: gli utenti possono selezionare le annotazioni di un documento per eliminare

  - Toggle trasparenza annotazione – rende le annotazioni semitrasparenti per visualizzare il contenuto dietro l'annotazione

  - Pagina precedente – consente di accedere alla pagina precedente

  - Pagina successiva – passa alla pagina successiva

  - Vai a pagina-l'utente può immettere un numero di pagina specifico per passare a

  - Zoom – impostare il livello di zoom per la visualizzazione annotazioni

  - Ruota – l'utente può ruotare il documento in senso orario

  - Search: l'utente può eseguire una ricerca in un documento e passare ai vari successi all'interno del documento
    
    ![Visualizzazione anNotazioni
    ](../media/Reviewimage1.png)

Si noti che queste annotazioni sono su dati raccolti come elementi di prova, non nel relativo percorso originale in Live System. 

## <a name="more-information"></a>Ulteriori informazioni

Nella tabella seguente sono elencati i limiti per le evidenze nelle indagini sui dati (Preview).  Tutti gli elementi che superano i valori massimi dei singoli file verranno visualizzati come errori di elaborazione.
    
  |**Descrizione del limite**|**Tipo di limite**|
  |:-----|:-----|
  |Numero massimo di raccolte di prove  <br/> |50  <br/> |
  |Numero totale di documenti che possono essere ingeriti in un caso (per tutte le raccolte di evidenze nell'inchiesta)  <br/> |1 milione  <br/> |
  |Dimensioni totali dei file per carico  <br/> |100 GB  <br/> |
  |Dimensioni massime di un singolo file   <br/> |100 MB  <br/> |
  |Numero massimo di caratteri estratti da un singolo file  <br/> |10 milioni  <br/> |
  |Profondità degli elementi incorporati in un documento  <br/> |25  <br/> |
  