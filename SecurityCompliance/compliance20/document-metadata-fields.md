---
title: Campi dei metadati del documento in Advanced eDiscovery (Preview)
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
ms.openlocfilehash: b9caf390e3ee0c10a35fa12cc68fcb0638987dcb
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32251854"
---
# <a name="document-metadata-fields-in-advanced-ediscovery-preview"></a>Campi dei metadati del documento in Advanced eDiscovery (Preview)

Nella tabella seguente sono elencati i campi dei metadati per i documenti in un working set in un caso in Advanced eDiscovery (Preview). La tabella indica il nome del campo metadati, se il campo può essere cercato durante l'esecuzione di una query in un working set, se il campo è presente quando si visualizzano i metadati dei file di un documento selezionato in un working set e se il campo è incluso quando i documenti vengono esportati. 

Nella tabella seguente sono elencati i campi dei metadati per i documenti in un working set in un caso in Advanced eDiscovery (Preview). La tabella indica il nome del campo metadati, se il campo può essere cercato durante l'esecuzione di una query in un working set, se il campo è presente quando si visualizzano i metadati dei file di un documento selezionato in un working set e se il campo è incluso quando i documenti vengono esportati. 

> [!NOTE]
> I valori racchiusi tra parentesi nella colonna **working set di ricerca** è il nome della proprietà che è possibile cercare. I valori racchiusi tra parentesi nella colonna dei **metadati visualizzabili in file** è il nome della proprietà visualizzata quando si visualizzano i metadati dei file.

|**Nome del campo** </br>|**Ricercabile in working set** |**Visualizzabile nei metadati dei file** |**Esportato** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Tag del caso                  | Sì (tag)                                      |                         | Sì         |
|Etichette di conformità          |                                                 |                         | Sì         |
|Percorso composto              |                                                 |                         | Sì         |
|ID contenitore               |                                                 |                         | Sì         |
|Indice di conversazione         |                                                 |                         | Sì         |
|Custode                  | Sì (custode)                                 |   Sì (custode)       | Sì         |
|Origine dati                | Sì (origine)                                    |   Sì (carico di lavoro)          | Sì         |
|Data                       | Sì (Data)                                      |   Sì (data UTC)        | Sì         |
|Percorso composto deduplicato      |                                                 |                         | Sì         |
|Depositari deduplicati         |                                                 |                         | Sì         |
|ID file deduplicati           |                                                 |                         | Sì         |
|Autori del documento                | Sì (autore) *                                   |    Sì (autore)         | Sì         |
|Commenti del documento               | Sì (commenti)                                  |                         | Sì         |
|Azienda doc                |                                                 |                         | Sì         |
|Data di creazione del documento           | Sì (createdTime) *                              |    Sì (tempo creato)   | Sì         |
|Data del documento modificata          | Sì (lastModifiedDate) *                         |                         | Sì         |
|Parole chiave del documento               |                                                 |                         | Sì         |
|Ultimo salvataggio del documento          |                                                 |                         | Sì         |
|Documento modificato da            |                                                 |                         | Sì         |
|Oggetto doc                |                                                 |  Sì (Subject/title)    | Sì         |
|Modello doc               |                                                 |                         | Sì         |
|Titolo del documento                  | Sì (titolo)                                     |  Sì (titolo)            | Sì         |
|Versione doc                |                                                 |                         | Sì         |
|Tema dominante             | Sì (dominantTheme)                             |  Sì (tema dominante)   | Sì         |
|Sottoinsieme duplicato           |                                                 |                         | Sì         |
|Azione di posta elettronica               |                                                 |                         | Sì         |
|Messaggi di posta elettronica Ccn                  | Sì (Ccn)                                       |                         | Sì         |
|Posta elettronica CC                   | Sì (CC)                                        |                         | Sì         |
|ID conversazione di posta elettronica      |                                                 |                         | Sì         |
|Data di ricezione della posta elettronica        | Sì (ricevuti)                                  |   Sì (ricevuti)        | Sì         |
|Data di invio della posta elettronica            | Sì (inviato)                                      |   Sì (inviato)            | Sì         |
|Il messaggio di posta elettronica è allegato       |                                                 |                         | Sì         |
|Importanza della posta elettronica           |                                                 |                         | Sì         |
|Intestazioni Internet di posta elettronica     |                                                 |                         | Sì         |
|Livello di posta elettronica                |                                                 |                         | Sì         |
|ID messaggio di posta elettronica           |                                                 |                         | Sì         |
|Domini dei partecipanti alla posta elettronica  | Sì (participantDomains)                        |                         | Sì         |
|Partecipanti alla posta elettronica         | Sì (partecipanti)                              |                         | Sì         |
|Domini del destinatario di posta elettronica    | Sì (recipientDomains)                          |                         | Sì         |
|Destinatari della posta elettronica           | Sì (destinatari)                                |                         | Sì         |
|Sicurezza della posta elettronica             |                                                 |                         | Sì         |
|Mittente del messaggio di posta elettronica               | Sì (mittente)                                    |   Sì (mittente)          | Sì         |
|Dominio del mittente del messaggio di posta elettronica        | Sì (senderDomain)                              |                         | Sì         |
|Sensibilità della posta elettronica          |                                                 |                         | Sì         |
|Set di messaggi di posta elettronica                  | Sì (emailSetId)                                |   Sì (EmailSetID)      | Sì         |
|Oggetto del messaggio di posta elettronica              | Sì (oggetto)                                   |   Sì (Subject/title)   | Sì         |
|Thread di posta elettronica               |                                                 |                         | Sì         |
|Posta elettronica a                   | Sì (a)                                        |                         | Sì         |
|Codice errore                 | Sì (processingStatus)                          |                         | Sì         |
|Esporta percorso nativo         |                                                 |                         | Sì         |
|Lunghezza del testo Estratto      |                                                 |                         | Sì         |
|Percorso testo Estratto        |                                                 |                         | Sì         |
|ID famiglia                  | Sì (familyId)                                  |   Sì (FamilyId)        | Sì         |
|Dimensione famiglia                |                                                 |                         | Sì         |
|Classe file                 | Sì (fileClass)                                 |   Sì (classe file)      | Sì         |
|ID file                    | Sì (fileId)                                    |   Sì (ID)              | Sì         |
|Contiene testo                   |                                                 |                         | Sì         |
|Tipo inclusivo             | Sì (inclusiveType)                             |   Sì (tipo incluso)  | Sì         |
|Data di ingresso modificata        |                                                 |                         | Sì         |
|ID file di input              |                                                 |                         | Sì         |
|Percorso di input                 |                                                 |                         | Sì         |
|ID messaggio Internet        |                                                 |                         | Sì         |
|È rappresentativo          | Sì (markAsRepresentative)                      |                         | Sì         |
|Classe Item                 |                                                 |                         | Sì         |
|ID di carico                    | Sì (loadId)                                    |                         | Sì         |
|Nome percorso              |                                                 |                         | Sì         |
|Contrassegnata come pivot            | Sì (markAsPivot)                               |   Sì (contrassegnata come pivot) | Sì         |
|Tipo di messaggio               | Sì (messageKind)                               |                         | Sì         |
|Estensione nativa           |                                                 |                         | Sì         |
|Nome file nativo           |                                                 |    Sì (nomefile)      | Sì         |
|MD5 nativo                 |                                                 |                         | Sì         |
|Nativo SHA 256             |                                                 |                         | Sì         |
|Dimensioni native                | Sì (dimensioni)                                      |   Sì (NativeSize)     | Sì         |
|Tipo nativo                | Sì (filetype)                                  |   Sì (tipo di file)       | Sì         |
|ND ET Sort escl     |                                                 |                         | Sì         |
|ND ET Sort incl Attach     |                                                 |                         | Sì         |
|Set ND                     |                                                 |                         | Sì         |
|Autori di O365               | Sì (autore) *                                   |   Sì (mittente/autore)   | Sì         |
|O365 creato da            |                                                 |                         | Sì         |
|Data di O365 creata          | Sì (createdTime) *                              |                         | Sì         |
|Data di O365 modificata         | Sì (lastModifiedDate) *                         |   Sì (data dell'Ultima modifica) | Sì      |
|O365 modificato da           |                                                 |                         | Sì         |
|Nodo padre                |                                                 |                         | Sì         |
|ID pivot                   | Sì (pivotId)                                   |  Sì (PivotID)          | Sì         |
|Numero destinatari            |                                                 |                         | Sì         |
|Numero di riga                 |                                                 |                         | Sì         |
|Imposta ID                     |                                                 |                         | Sì         |
|Impostare l'ordine inclusivo per primo |                                                 |                         | Sì         |
|Percentuale di somiglianza         |                                                 |                         | Sì         |
|Elenco temi                | Sì (temi)                                | Sì (elenco temi)       | Sì         |
|Word count                 | Sì (wordCount)                                 |                         | Sì         |
|Punteggio di pertinenza (problema)    | Sì (relevanceScore_issueNum)                   |                         | Sì           |
|Lettura percentile (problema)    | Sì (readPercentile_issueNum)                   |                         | Sì          |
|Tag pertinenza (problema)      | Sì (relevanceTag_issueNum)                     |                         | Sì           |
|||||

  \*Per questi campi, se all'interno di un documento sono presenti valori incorporati, la ricerca darà la priorità a tali valori. in caso contrario, tenterà di visualizzare il valore di Office 365.