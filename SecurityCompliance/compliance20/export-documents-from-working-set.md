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
# <a name="export-documents-from-a-working-set"></a><span data-ttu-id="2ff4a-102">Esportare documenti da un set di lavoro</span><span class="sxs-lookup"><span data-stu-id="2ff4a-102">Export documents from a working set</span></span>

<span data-ttu-id="2ff4a-103">L'esportazione di contenuto da un working set può essere eseguita tramite tre diversi metodi:</span><span class="sxs-lookup"><span data-stu-id="2ff4a-103">Exporting content from a working set can be accomplished via 3 different methods:</span></span>

## <a name="download"></a><span data-ttu-id="2ff4a-104">Download</span><span class="sxs-lookup"><span data-stu-id="2ff4a-104">Download</span></span>

<span data-ttu-id="2ff4a-105">Download offre un modo semplice per scaricare il contenuto da un working set in formato nativo.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-105">Download offers a simple way to download content from a working set in Native format.</span></span> <span data-ttu-id="2ff4a-106">Sfrutta le caratteristiche di trasferimento dei dati del browser in modo che una richiesta del browser venga visualizzata una volta che il download è pronto.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-106">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="2ff4a-107">I file scaricati con questo metodo verranno zippati in un file contenitore e saranno file a livello di elemento.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-107">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="2ff4a-108">Questo significa che se si seleziona un allegato, verrà visualizzato automaticamente il messaggio di posta elettronica con l'allegato incluso.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-108">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="2ff4a-109">Analogamente, se si seleziona un foglio di calcolo di Excel incorporato in un documento di Word, verrà visualizzato il documento di Word con il foglio di calcolo di Excel incorporato.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-109">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="2ff4a-110">Gli elementi scaricati conserveranno la data dell'Ultima modifica che può essere visualizzata come proprietà di un file.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-110">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="2ff4a-111">Per scaricare il contenuto da un working set, iniziare selezionando i file che si desidera scaricare, quindi selezionare "Scarica" dal menu azioni.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-111">To download content from a working set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Schermata di una descrizione del computer generata automaticamente](../media/eDiscoDownload.png)

## <a name="export"></a><span data-ttu-id="2ff4a-113">Esportazione</span><span class="sxs-lookup"><span data-stu-id="2ff4a-113">Export</span></span>

<span data-ttu-id="2ff4a-114">Export consente agli utenti di personalizzare il contenuto incluso nel pacchetto di download.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-114">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="2ff4a-115">Fornisce una pagina di configurazione con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2ff4a-115">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="2ff4a-116">File di metadati</span><span class="sxs-lookup"><span data-stu-id="2ff4a-116">Metadata file</span></span>

> <span data-ttu-id="2ff4a-117">Questo può essere considerato come il "Load file" che contiene i metadati associati ai file esportati.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-117">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="2ff4a-118">Per un elenco dei campi disponibili nel file di metadati, vedere \[link\].</span><span class="sxs-lookup"><span data-stu-id="2ff4a-118">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="2ff4a-119">Questo file può in genere essere ingerito da<sup></sup> 3 strumenti di terze parti a valle.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-119">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="2ff4a-120">Dati tag</span><span class="sxs-lookup"><span data-stu-id="2ff4a-120">Tag data</span></span>

> <span data-ttu-id="2ff4a-121">Questo contenuto verrebbe aggiunto come campi nel file di metadati.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-121">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="2ff4a-122">Contiene tutte le informazioni sui tag applicate nei set di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-122">It contains all of the tag information applied in working sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="2ff4a-123">File di testo</span><span class="sxs-lookup"><span data-stu-id="2ff4a-123">Text files</span></span>

> <span data-ttu-id="2ff4a-124">È possibile generare file di testo per ogni file esportato da un working set.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-124">Text files can be generated for each file exported from a working set.</span></span> <span data-ttu-id="2ff4a-125">Spesso questi file sono necessari per i partner del servizio come parte dell'ingestione dei dati<sup></sup> in 3 strumenti di terze parti a valle.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-125">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="2ff4a-126">File redatti</span><span class="sxs-lookup"><span data-stu-id="2ff4a-126">Redacted files</span></span>

> <span data-ttu-id="2ff4a-127">Se durante la revisione vengono generati file PDF ritirati, questi sono disponibili durante l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-127">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="2ff4a-128">Gli utenti possono decidere se esportare solo i file nativi o sostituire i nativi che dispongono di redazioni con il masterizzato nei file PDF.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-128">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="2ff4a-129">Percorso di esportazione</span><span class="sxs-lookup"><span data-stu-id="2ff4a-129">Export Location</span></span>

> <span data-ttu-id="2ff4a-130">Il contenuto esPortato viene recapitato a un BLOB di Azure fornito da Microsoft o è possibile utilizzare il BLOB di un cliente se i dettagli vengono forniti all'esportazione.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-130">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

## <a name="export-structure"></a><span data-ttu-id="2ff4a-131">Struttura di esportazione</span><span class="sxs-lookup"><span data-stu-id="2ff4a-131">Export Structure</span></span>

<span data-ttu-id="2ff4a-132">Quando il contenuto viene esportato da un working set, il contenuto è organizzato nella struttura seguente.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-132">When content is exported from a working set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="2ff4a-133">Cartella radice-ID download</span><span class="sxs-lookup"><span data-stu-id="2ff4a-133">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="2ff4a-134">Esporta\_caricamento\_file. csv = file di metadati</span><span class="sxs-lookup"><span data-stu-id="2ff4a-134">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="2ff4a-135">Summary. txt = un file di riepilogo con statistiche di esportazione</span><span class="sxs-lookup"><span data-stu-id="2ff4a-135">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="2ff4a-136">Input\_o file\_nativi = contiene tutti i file nativi</span><span class="sxs-lookup"><span data-stu-id="2ff4a-136">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="2ff4a-137">File\_Error = contiene eventuali file di errore inclusi nell'esportazione</span><span class="sxs-lookup"><span data-stu-id="2ff4a-137">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="2ff4a-138">ExtractionError – un CSV che contiene i metadati disponibili di file che non sono stati estratti correttamente dai file padre</span><span class="sxs-lookup"><span data-stu-id="2ff4a-138">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="2ff4a-139">ProcessingError – contenuto con errori di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-139">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="2ff4a-140">Questo contenuto è a livello di elemento significato se un allegato ha subito un errore di elaborazione, il messaggio di posta elettronica che contiene l'allegato verrà incluso in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-140">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="2ff4a-141">File\_di\_testo estratti = contiene tutti i file di testo estratti generati durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-141">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>

## <a name="working-set"></a><span data-ttu-id="2ff4a-142">Working set</span><span class="sxs-lookup"><span data-stu-id="2ff4a-142">Working Set</span></span>

<span data-ttu-id="2ff4a-143">È possibile aggiungere contenuto a un altro working set.</span><span class="sxs-lookup"><span data-stu-id="2ff4a-143">Content can be added to another working set.</span></span>