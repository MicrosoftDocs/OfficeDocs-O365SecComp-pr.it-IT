---
title: Esportare documenti da un set di lavoro
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
ms.openlocfilehash: 815b92b13ed09d8aec64f5207f1c82d910e2dce0
ms.sourcegitcommit: 9f38ba72eba0b656e507860ca228726e4199f7ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2019
ms.locfileid: "30475706"
---
# <a name="export-documents-from-a-working-set"></a>Esportare documenti da un set di lavoro

L'esportazione di contenuto da un working set può essere eseguita tramite tre diversi metodi:

## <a name="download"></a>Download

Download offre un modo semplice per scaricare il contenuto da un working set in formato nativo. Sfrutta le caratteristiche di trasferimento dei dati del browser in modo che una richiesta del browser venga visualizzata una volta che il download è pronto. I file scaricati con questo metodo verranno zippati in un file contenitore e saranno file a livello di elemento. Questo significa che se si seleziona un allegato, verrà visualizzato automaticamente il messaggio di posta elettronica con l'allegato incluso. Analogamente, se si seleziona un foglio di calcolo di Excel incorporato in un documento di Word, verrà visualizzato il documento di Word con il foglio di calcolo di Excel incorporato. Gli elementi scaricati conserveranno la data dell'Ultima modifica che può essere visualizzata come proprietà di un file.

Per scaricare il contenuto da un working set, iniziare selezionando i file che si desidera scaricare, quindi selezionare "Scarica" dal menu azioni.

![Schermata di una descrizione del computer generata automaticamente](../media/eDiscoDownload.png)

## <a name="export"></a>Esportazione

Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download. Fornisce una pagina di configurazione con le seguenti impostazioni:

### <a name="metadata-file"></a>File di metadati

> Questo può essere considerato come il "Load file" che contiene i metadati associati ai file esportati. Per un elenco dei campi disponibili nel file di metadati, vedere \[link\]. Questo file può in genere essere ingerito da<sup></sup> 3 strumenti di terze parti a valle.

### <a name="tag-data"></a>Dati tag

> Questo contenuto verrebbe aggiunto come campi nel file di metadati. Contiene tutte le informazioni sui tag applicate nei set di lavoro.

### <a name="text-files"></a>File di testo

> È possibile generare file di testo per ogni file esportato da un working set. Spesso questi file sono necessari per i partner del servizio come parte dell'ingestione dei dati<sup></sup> in 3 strumenti di terze parti a valle.

### <a name="redacted-files"></a>File redatti

> Se durante la revisione vengono generati file PDF ritirati, questi sono disponibili durante l'esportazione. Gli utenti possono decidere se esportare solo i file nativi o sostituire i nativi che dispongono di redazioni con il masterizzato nei file PDF.

### <a name="export-location"></a>Percorso di esportazione

> Il contenuto esPortato viene recapitato a un BLOB di Azure fornito da Microsoft o è possibile utilizzare il BLOB di un cliente se i dettagli vengono forniti all'esportazione.

## <a name="export-structure"></a>Struttura di esportazione

Quando il contenuto viene esportato da un working set, il contenuto è organizzato nella struttura seguente.

  - Cartella radice-ID download
    
      - Esporta\_caricamento\_file. csv = file di metadati
    
      - Summary. txt = un file di riepilogo con statistiche di esportazione
    
      - Input\_o file\_nativi = contiene tutti i file nativi
    
      - File\_Error = contiene eventuali file di errore inclusi nell'esportazione
        
          - ExtractionError – un CSV che contiene i metadati disponibili di file che non sono stati estratti correttamente dai file padre
        
          - ProcessingError – contenuto con errori di elaborazione. Questo contenuto è a livello di elemento significato se un allegato ha subito un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato verrà incluso in questa cartella.
    
      - File\_di\_testo estratti = contiene tutti i file di testo estratti generati durante l'elaborazione.

## <a name="working-set"></a>Working set

È possibile aggiungere contenuto a un altro working set.