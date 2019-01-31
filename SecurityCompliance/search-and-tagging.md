---
title: Ricerca e aggiunta di tag
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta.
ms.openlocfilehash: 013e559ca55e9a877dfb2f8747c4696f81e1e095
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666146"
---
# <a name="search-and-tagging"></a>Ricerca e aggiunta di tag

In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta. Per una dimostrazione breve di ricerca e l'assegnazione dei tag, vedere il video di [gestione dei dati con eDiscovery avanzate](https://www.youtube.com/watch?v=VaPYL3DHP6I) .

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Cercare i documenti nel case

Dopo avere elaborate documenti in un caso eDiscovery avanzate (e se lo si desidera eseguire la funzionalità di analisi o pertinenza), è possibile utilizzare la ricerca e utilizzo dei tag per cercare i documenti e quindi organizzare i contatti tramite l'applicazione di tag specifico (denominato anche le etichette). È possibile definire una query di ricerca tramite schede fornito condizione o condizione scheda utilizzando un linguaggio di query KQL simili le parole chiave. Sintassi KQL comune, ad esempio AND, OR, NOT, e NEAR(n) sono supportati, nonché finale più caratteri jolly (*). 

Nella tabella seguente sono elencate le proprietà che è possibile cercare per l'utilizzo di una query con parole chiave KQL. In alternativa, è possibile utilizzare una scheda condizione per di eDiscovery avanzate dello strumento di ricerca per aggiungere una condizione (per le proprietà selezionate) a una query di ricerca.

|**Proprietà**|**Descrizione**|
|:-----|:-----|
|**caselabel** <br/> | Il nome del tag creato/applicato quando viene contrassegnato come un documento. <br/> |
|**depositaria** <br/> | Depositaria associata a un documento. soggetta a limitazioni. <br/> |
|**Data** <br/> | Inviati data per la posta elettronica; Data di modifica di documenti del sito. <br/> |
|**fileid** <br/> | ID di File all'interno del case. <br/> |
|**tipo di file** <br/> | Estensione di file nativo. <br/> |
|**fileclass** <br/> | Posta elettronica, documenti o degli allegati. <br/> |
|**senderauthor** <br/> | Il mittente per la posta elettronica; creazione di documenti del sito. <br/> |
|**dimensioni** <br/> | La dimensione del file in KB. <br/> |
|**si** <br/> | L'oggetto per la posta elettronica; il titolo di documenti del sito. <br/> |
|**bcc** <br/> | Il campo Ccn di un messaggio di posta elettronica. <br/> |
|**cc** <br/> | Il campo Cc di un messaggio di posta elettronica. <br/> |
|**partecipanti** <br/> | L'indirizzo di posta elettronica di tutti i partecipanti a un thread di posta elettronica, inclusi i collegamenti mancante. <br/> |
|**ricevuta** <br/> | Data che è stato ricevuto un messaggio di posta elettronica. <br/> |
|**destinatari** <br/> | Destinatari di un messaggio di posta elettronica, inclusi su a, Cc o Ccn campi. <br/> |
|**mittente** <br/> | Il mittente di un messaggio di posta elettronica. <br/> |
|**LastModifiedDate** <br/> | L'ultima data di un documento di un sito. <br/> |
|**inviati** <br/> | Data di invio di un messaggio di posta elettronica. <br/> |
|**A** <br/> | Il destinatario elencato nel campo a di un messaggio di posta elettronica. <br/> |
|**autore** <br/> | L'autore di un documento di un sito. <br/> |
|**titolo** <br/> | Il titolo di un documento di un sito. <br/> |
|**dominanttheme**\* <br/> | Il tema dominante di un elemento. <br/> |
|**themeslist**\* <br/> | Temi associati a un elemento. <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | Percentile lettura di un elemento per il rilascio definito da [issuenum]. <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | Il punteggio di pertinenza di un elemento per il rilascio definito da [issuenum]. <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | Se un elemento è stato contrassegnato manualmente la pertinenza, il tag definito dalla [tagname]. <br/> |
|||

\*È disponibile solo se è stato eseguito il modulo di temi.

\*\*È disponibile solo se è stato eseguito il modulo di pertinenza.

In alternativa, è possibile utilizzare una scheda condizione di eDiscovery avanzate dello strumento di ricerca per aggiungere una condizione (per le proprietà selezionate) a una query di ricerca. La schermata seguente mostra le condizioni che possono essere aggiunti a una query. Nella colonna **gruppo** indica se la proprietà si applica al messaggio di posta elettronica, documenti del sito o a entrambi (indicata dal valore *comune*). Questa colonna vengono indicati le proprietà supportano la ricerca sono disponibili dopo l'esecuzione del modulo di pertinenza.

![I criteri di ricerca nello strumento di ricerca avanzata eDiscovery](media/AeDSearchConditions.png)

Per ulteriori informazioni sulle proprietà di ricerca, vedere [query con parole chiave e le condizioni di ricerca](keyword-queries-and-search-conditions.md).
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging e formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

