---
title: Creare una query per individuare dati riservati memorizzati nei siti
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: Prevenzione di perdita di dati (DLP) in SharePoint Online, consente di individuare i documenti che contengono dati sensibili in tutto il tenant. Dopo l'individuazione dei documenti, è possibile utilizzare i proprietari di documento per proteggere i dati. In questo argomento consentono di una query di ricerca di dati riservati del modulo.
ms.openlocfilehash: c30cb2e4b93e1a7db90f3e3f922f406285c6f692
ms.sourcegitcommit: 81e06e09bf5ca8e3f51b164d6251b1c35b3285cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "25829187"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Creare una query per individuare dati riservati memorizzati nei siti

Gli utenti spesso archiviano dati riservati, ad esempio numeri di carta di credito, previdenza sociale, o personale, nei propri siti e nel tempo si può esporre un'organizzazione di grave rischio di perdite di dati. Documenti archiviati nei siti, inclusi OneDrive per i siti, potrebbe essere condivisi con utenti esterni all'organizzazione che non dispongono dell'accesso alle informazioni. Prevenzione di perdita di dati (DLP) in SharePoint Online, consente di individuare i documenti che contengono dati sensibili in tutto il tenant. Dopo l'individuazione dei documenti, è possibile utilizzare i proprietari di documento per proteggere i dati. In questo argomento consentono di una query di ricerca di dati riservati del modulo.
  
> [!NOTE]
> Electronic discovery, o eDiscovery e DLP sono caratteristiche che richiedono [SharePoint Online piano 2](https://go.microsoft.com/fwlink/?LinkId=510080). 
  
## <a name="forming-a-basic-dlp-query"></a>Creazione di una query DLP di base

Esistono tre parti che compongono una base query DLP: SensitiveType, contare intervallo e l'intervallo di confidenza. Come illustrato nel grafico seguente **SensitiveType: "\<tipo\>"** non è necessaria ed entrambe**|\<contare intervallo\> ** e**|\<intervallo di confidenza\> ** sono facoltativi. 
  
![Query di esempio divisa in necessaria e facoltativa](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>SensitiveType - obbligatorio

Qual è ogni parte? Le query di SharePoint DLP in genere iniziano con la proprietà `SensitiveType:"` e un tipo di informazioni denominare da [tipi di informazioni riservate inventario](https://go.microsoft.com/fwlink/?LinkID=509999)e terminare con un `"`. È inoltre possibile utilizzare il nome del [tipo di informazione sensibile personalizzato](create-a-custom-sensitive-information-type.md) creato per l'organizzazione. Ad esempio, che si stia cercando per i documenti che contengono numeri di carta di credito. In un'istanza, utilizzare il seguente formato: `SensitiveType:"Credit Card Number"`. Dal momento che non vengono conteggio intervallo o un intervallo di confidenza, sarà la query restituisce tutti i documenti in cui viene rilevato un numero di carta di credito. Si tratta della query più semplice che è possibile eseguire e restituisce la maggior parte dei risultati. Tenere presente che condivide il controllo ortografico e spaziatura del tipo di riservati. 
  
### <a name="ranges---optional"></a>Intervalli - facoltativo

Entrambe le due parti sono intervalli, possiamo esaminare rapidamente l'aspetto di un intervallo. Nelle query di SharePoint DLP, un intervallo di base è rappresentato da due numeri separati da due punti, che è simile al seguente: `[number]..[number]`. Ad esempio, se `10..20` viene utilizzato, numeri compresi tra 10 e 20 consente di catturare quell'intervallo. Esistono molte combinazioni di intervallo diverso e alcuni sono descritte in questo argomento. 
  
Possibile aggiungere un intervallo di conteggio alla query. È possibile utilizzare il conteggio intervallo per definire il numero di occorrenze di informazioni riservate che un documento deve contenere prima che venga incluso nei risultati della query. Ad esempio, se si desidera che la query per restituire solo i documenti che contengono numeri di carta di credito esattamente cinque, utilizzare questo: `SensitiveType:"Credit Card Number|5"`. Intervallo numero consentono inoltre di identificare i documenti che comportano elevate livelli di rischio. L'organizzazione potrebbe si consideri ad esempio i documenti con cinque o più numeri di carta di credito ad alto rischio. Per trovare documenti adattando questo criterio, è necessario utilizzare la query seguente: `SensitiveType:"Credit Card Number|5.."`. In alternativa, è possibile trovare i documenti con cinque o massimo i numeri di carta di credito utilizzando questa query: `SensitiveType:"Credit Card Number|..5"`. 
  
#### <a name="confidence-range"></a>Intervallo di confidenza

Infine, l'intervallo di confidenza è il livello di probabilità che il tipo di sensibile rilevato sia effettivamente una corrispondenza. I valori per l'intervallo di confidenza Analogamente a quanto avviene per contare intervallo. È possibile formare una query senza includere un intervallo di numero. Ad esempio, per la ricerca dei documenti con un numero qualsiasi di numeri di carta di credito, purché l'intervallo di confidenza 85% o superiore, è necessario utilizzare la query seguente: `SensitiveType:"Credit Card Number|*|85.."`. 
  
> [!IMPORTANT]
> L'asterisco ( `*`) è un carattere jolly significa works alcun valore. È possibile utilizzare il carattere jolly ( `*`) dell'intervallo numero o dell'intervallo di confidenza, ma non in un tipo di riservati. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Ulteriori proprietà della query e operatori di ricerca sono disponibili nel Centro eDiscovery

DLP in SharePoint vengono inoltre presentati LastSensitiveContentScan proprietà, che consente di cercare i file di ricerca di virus all'interno di un periodo di tempo specificato. Per esempi di query con la `LastSensitiveContentScan` proprietà, vedere gli [esempi di query complesse](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) nella sezione successiva. 
  
È possibile utilizzare non solo proprietà specifiche del DLP per creare una query, ma anche proprietà di ricerca di eDiscovery SharePoint standard, ad esempio `Author` o `FileExtension`. È possibile utilizzare operatori per creare query complesse. Per l'elenco degli operatori e proprietà disponibili, vedere post di blog [utilizzando le proprietà di ricerca e gli operatori con eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) . 
  
## <a name="examples-of-complex-queries"></a>Esempi

Negli esempi seguenti utilizzano diversi tipi di riservate, proprietà e gli operatori per illustrare come è possibile filtrare le query per trovare esattamente ciò che sta cercando.
  
|**Query**|**Spiegazione**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |Il nome potrebbe sembrare strano perché è molto tempo, ma è il nome corretto per il tipo riservato. Assicurarsi di utilizzare i nomi esatti di [inventario dei tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999). È inoltre possibile utilizzare il nome del [tipo di informazione sensibile personalizzato](create-a-custom-sensitive-information-type.md) creato per l'organizzazione.<br/> |
| ' SensitiveType: "numero di carta di credito|1..4294967295|1..100"' <br/> |Restituire i documenti con almeno una corrispondenza per il tipo di sensibile "Numero di carta di credito." I valori per ogni intervallo sono i rispettivi valori massimi e minimi. Un modo più semplice scrivere la query viene `SensitiveType:"Credit Card Number"`, ma in cui è divertimento in cui?<br/> |
| ' SensitiveType: "numero di carta di credito| 5..25" e LastSensitiveContentScan:"8/11/2018..8/13/2018 "' <br/> |Restituisce i documenti con i numeri di carta di credito 5 25 che sono stati analizzati da 11 agosto 2018 13 agosto 2018.  <br/> |
| ' SensitiveType: "numero di carta di credito| 5..25" e LastSensitiveContentScan:"8/11/2018..8/13/2018 "non FileExtension:XLSX' <br/> |Restituisce i documenti con i numeri di carta di credito 5 25 che sono stati analizzati da 11 agosto 2018 13 agosto 2018. I file con estensione XLSX non vengono inclusi nei risultati della query.  `FileExtension` è una delle numerose proprietà che è possibile includere in una query. Per ulteriori informazioni, vedere [utilizzo di proprietà di ricerca e gli operatori con eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |In questo modo vengono restituiti i documenti che contengono sia un numero di carta di credito che un numero di previdenza sociale.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Esempi

Non tutte le query sono uguali. Nella tabella seguente vengono forniti alcuni esempi di query che non funzionano con DLP in SharePoint e descrive il motivo del.
  
|**Query non supportate**|**Motivo**|
|:-----|:-----|
| ' SensitiveType: "numero di carta di credito|.." ` <br/> |Aggiungere almeno un numero.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" non è un nome di tipo riservati valido. Solo i nomi inclusi nell' [inventario dei tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999) funzionano nelle query DLP.<br/> |
| ' SensitiveType: "numero di carta di credito|0"' <br/> |Zero non è valido come valore minimo o il valore massimo in un intervallo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Si potrebbe essere difficile vedere, ma è disponibile spazio vuoto tra "Credito" e "Scheda" che effettua la query non valida. Utilizzare i nomi dei tipi di sensibili esatto dell' [inventario dei tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999).<br/> |
| ' SensitiveType: "numero di carta di credito|1.. 3"' <br/> |La parte di due periodi non deve essere separata da uno spazio.  <br/> |
| ' SensitiveType: "numero di carta di credito| |1..|"80.." <br/> |Esistono troppi pipe delimitatori (|). Attenersi invece il seguente formato: "SensitiveType:"numero di carta di credito|1..|"80.." <br/> |
| ' SensitiveType: "numero di carta di credito|1..|80..101"' <br/> |Poiché i valori di attendibilità rappresentano una percentuale, non possono superare 100. Al contrario, selezionare un numero compreso tra 1 e 100.  <br/> |
   
## <a name="for-more-information"></a>Ulteriori informazioni

[Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md)
  
[Eseguire una ricerca di contenuto in Office 365 protezione &amp; centro conformità](run-a-content-search-in-the-security-and-compliance-center.md)
  
[Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
  

