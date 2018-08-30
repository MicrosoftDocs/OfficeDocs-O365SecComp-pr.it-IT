---
title: Ricerca e aggiunta di tag
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta.
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530880"
---
# <a name="search-and-tagging"></a>Ricerca e aggiunta di tag

In eDiscovery avanzate, la funzionalità di ricerca e utilizzo dei tag consente di ricercare, visualizzare in anteprima e organizzare i documenti nel case. In questo modulo è attualmente disponibile la versione beta.

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Cercare i documenti nel case

Una volta che viene elaborata documenti di eDiscovery avanzate e se lo si desidera eseguire la funzionalità di analisi o il modulo di pertinenza, è possibile utilizzare la ricerca e utilizzo dei tag per cercare i documenti nel caso e organizzare i contatti utilizzando i tag specifico. È possibile definire la query utilizzando le schede condizione specificata o tramite un linguaggio di query KQL simili le parole chiave condizione scheda. Sintassi KQL comune, ad esempio AND, OR, NOT, e NEAR(n) sono supportati, nonché finale più caratteri jolly (*). Queste proprietà sono supportate nel nome della proprietà language query:

- caselabel: creato/applicati tag nel servizio di ricerca e utilizzo dei tag di questo case 
- depositari: depositari assegnati nel caso - soggetta a limitazioni
- Data: data per la posta elettronica inviati, data per i documenti di modifica
- fileid: ID del file all'interno del case
- FileType: estensione nativa
- fileclass: messaggio di posta elettronica, documenti o degli allegati
- senderauthor: mittenti di messaggi di posta elettronica, autore per i documenti
- dimensione: dimensione del file in KB
- si: interesse per i messaggi di posta elettronica, il titolo per i documenti
- bcc
- cc
- i partecipanti: gli indirizzi di tutti i partecipanti in un thread di posta elettronica, inclusi i collegamenti mancanti della posta elettronica
- ricevuti: data di ricezione
- destinatari: i nomi dei destinatari o gli indirizzi (a, cc, Ccn) di posta elettronica
- mittente
- LastModifiedDate: data di un documento dell'ultima modifica
- inviati: data di un messaggio di posta elettronica inviati
- a
- Author: creazione di un messaggio di posta elettronica
- titolo: titolo di un documento
- dominanttheme: tema dominante di un elemento\*
- themeslist: temi associati a un elemento\*
- readpercentile_ [issuenum]: leggere percentile di un elemento di problema [issuenum]\*\*
- relevancescore_ [issuenum]: punteggio di pertinenza di un elemento di problema [issuenum]\*\*
- relevancetag_ [issuenum]: se un elemento è stato contrassegnato manualmente la pertinenza, il tag per [issuenum]\*\*

\*Disponibile solo se è stato eseguito il modulo di temi \* \* è disponibile solo se è stato eseguito il modulo di pertinenza
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging e formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Test di analisi di pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

