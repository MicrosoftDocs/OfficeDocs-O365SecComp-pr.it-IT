---
title: Creare una query per individuare dati riservati memorizzati nei siti
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: Con la prevenzione della perdita di dati (DLP) in SharePoint Online, è possibile individuare i documenti che contengono dati riservati in tutto il tenant. Dopo aver scoperto i documenti, è possibile collaborare con i proprietari dei documenti per proteggere i dati. Questo argomento consente di creare una query per la ricerca di dati riservati.
ms.openlocfilehash: 3dc1081d4627f1a26c50eed84f733c31a3f6c194
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217236"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Creare una query per individuare dati riservati memorizzati nei siti

Gli utenti spesso archiviano dati riservati, ad esempio numeri di carta di credito, numeri di previdenza sociale o personali, nei rispettivi siti e, nel tempo, possono esporre un'organizzazione a rischi significativi di perdita di dati. I documenti archiviati nei siti, inclusi i siti di OneDrive for business, possono essere condivisi con utenti esterni all'organizzazione che non devono avere accesso alle informazioni. Con la prevenzione della perdita di dati (DLP) in SharePoint Online, è possibile individuare i documenti che contengono dati riservati in tutto il tenant. Dopo aver scoperto i documenti, è possibile collaborare con i proprietari dei documenti per proteggere i dati. Questo argomento consente di creare una query per la ricerca di dati riservati.
  
> [!NOTE]
> Electronic Discovery, o eDiscovery e DLP sono funzionalità Premium che richiedono [SharePoint Online piano 2](https://go.microsoft.com/fwlink/?LinkId=510080). 
  
## <a name="forming-a-basic-dlp-query"></a>Creazione di una query DLP di base

Sono disponibili tre parti che costituiscono una query DLP di base: SensitiveType, Range count e intervallo di confidenza. Come illustrato nella figura seguente, **SensitiveType: "\<\>tipo"** è obbligatorio e entrambi**|\<\> ** gli intervalli di conteggio e di**|\<\> confidenza** sono facoltativi. 
  
![Query di esempio divisa in necessaria e facoltativa](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>SensitiveType - obbligatorio

Che cos'è ogni parte? La proprietà `SensitiveType:"` e il nome di un tipo di informazioni vengono in genere iniziati con le query di SharePoint DLP dall'inventario dei `"`tipi di [informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999)e terminano con un. È inoltre possibile utilizzare il nome di un [tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md) creato per l'organizzazione. Ad esempio, è possibile cercare documenti contenenti numeri di carta di credito. In tal caso, è necessario utilizzare il formato seguente: `SensitiveType:"Credit Card Number"`. Poiché non è stato incluso l'intervallo di conteggio o la riservatezza, la query restituisce tutti i documenti in cui viene rilevato un numero di carta di credito. Questa è la query più semplice che è possibile eseguire e restituisce la maggior parte dei risultati. Tenere presente che l'ortografia e la spaziatura del tipo sensibile sono importanti. 
  
### <a name="ranges---optional"></a>Intervalli - facoltativo

Entrambe le due parti successive sono intervalli, quindi esaminiamo rapidamente l'aspetto di un intervallo. Nelle query di SharePoint DLP, un intervallo di base è rappresentato da due numeri separati da due periodi, che sono analoghi a quanto segue: `[number]..[number]`. Ad esempio, se `10..20` viene utilizzato, quell'intervallo catturerà i numeri da 10 a 20. Sono disponibili molte diverse combinazioni di intervalli e diverse sono descritte in questo argomento. 
  
Aggiungere un intervallo di count alla query. È possibile utilizzare l'intervallo di Count per definire il numero di occorrenze di informazioni riservate che un documento deve contenere prima che sia incluso nei risultati della query. Ad esempio, se si desidera che la query restituisca solo i documenti che contengono esattamente cinque numeri di carta di credito `SensitiveType:"Credit Card Number|5"`, utilizzare la seguente operazione:. L'intervallo di conteggio può anche facilitare l'identificazione dei documenti che presentano livelli elevati di rischio. Ad esempio, l'organizzazione potrebbe prendere in considerazione documenti con cinque o più numeri di carta di credito a rischio elevato. Per trovare i documenti che corrispondono a questo criterio, è necessario utilizzare `SensitiveType:"Credit Card Number|5.."`la query seguente:. In alternativa, è possibile trovare documenti con cinque o meno numeri di carta di credito utilizzando la query `SensitiveType:"Credit Card Number|..5"`seguente:. 
  
#### <a name="confidence-range"></a>Intervallo di confidenza

Infine, l'intervallo di confidenza è il livello di probabilità che il tipo sensibile rilevato sia effettivamente una corrispondenza. I valori per l'intervallo di confidenza funzionano in modo analogo all'intervallo di Count. È possibile creare una query senza includere un intervallo di conteggio. Ad esempio, per cercare i documenti con un numero qualsiasi di numeri di carta di credito, purché l'intervallo di confidenza sia pari o superiore al 85%, è `SensitiveType:"Credit Card Number|*|85.."`necessario utilizzare la query seguente:. 
  
> [!IMPORTANT]
> L'asterisco ( `*`) è un carattere jolly che indica che viene utilizzato qualsiasi valore. È possibile utilizzare il carattere jolly ( `*`) nell'intervallo di conteggio o nell'intervallo di confidenza, ma non in un tipo riservato. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Ulteriori proprietà della query e operatori di ricerca sono disponibili nel Centro eDiscovery

DLP in SharePoint introduce anche la proprietà LastSensitiveContentScan, che consente di cercare i file analizzati in un intervallo di tempo specifico. Per gli esempi di query `LastSensitiveContentScan` con la proprietà, vedere gli [esempi di query complesse](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) nella sezione successiva. 
  
È possibile utilizzare non solo le proprietà specifiche di DLP per creare una query, ma anche le proprietà di ricerca di eDiscovery `Author` di `FileExtension`SharePoint standard, ad esempio o. È possibile utilizzare gli operatori per creare query complesse. Per l'elenco delle proprietà e degli operatori disponibili, vedere l'articolo [utilizzo di proprietà e operatori di ricerca con](https://go.microsoft.com/fwlink/?LinkId=510093) il post di Blog di eDiscovery. 
  
## <a name="examples-of-complex-queries"></a>Esempi

Negli esempi seguenti vengono utilizzati diversi tipi, proprietà e operatori sensibili per illustrare in che modo è possibile affinare le query per trovare esattamente ciò che si sta cercando.
  
|**Query**|**Spiegazione**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |Il nome potrebbe sembrare strano perché è così lungo, ma è il nome corretto per quel tipo di sensibili. Assicurarsi di utilizzare nomi esatti dall'inventario dei [tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999). È inoltre possibile utilizzare il nome di un [tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md) creato per l'organizzazione.<br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |In questo modo vengono restituiti documenti con almeno una corrispondenza al tipo sensibile "numero di carta di credito". I valori per ogni intervallo sono i rispettivi valori minimo e massimo. Un modo più semplice per scrivere questa query è `SensitiveType:"Credit Card Number"`, ma qual è il divertimento in questo?<br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |Restituisce documenti con 5-25 numeri di carta di credito che sono stati analizzati dall'11 agosto 2018 al 13 agosto 2018.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |Restituisce documenti con 5-25 numeri di carta di credito che sono stati analizzati dall'11 agosto 2018 al 13 agosto 2018. I file con estensione XLSX non sono inclusi nei risultati della query.  `FileExtension` è una delle numerose proprietà che è possibile includere in una query. Per ulteriori informazioni, vedere [utilizzo di proprietà e operatori di ricerca con eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |In questo modo vengono restituiti i documenti che contengono sia un numero di carta di credito che un numero di previdenza sociale.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Esempi

Non tutte le query vengono create uguali. Nella tabella seguente vengono forniti esempi di query che non funzionano con DLP in SharePoint e viene descritto il motivo.
  
|**Query non supportate**|**Motivo**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |Aggiungere almeno un numero.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" non è un nome di tipo sensibile valido. Solo i nomi dei [tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999) funzionano nell'inventario delle query DLP.<br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |Zero non è valido come valore minimo o valore massimo di un intervallo.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Potrebbe essere difficile da vedere, ma c'è spazio vuoto supplementare tra "credito" e "carta" che rende la query non valida. Utilizzare nomi di tipo sensibili esatti dall' [inventario dei tipi di informazioni riservate](https://go.microsoft.com/fwlink/?LinkID=509999).<br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |La parte di due periodi non deve essere separata da uno spazio.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |Sono presenti troppi delimitatori di pipe (|). Seguire questo formato invece:`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |Poiché i valori di sicurezza rappresentano una percentuale, non possono superare 100. Scegliere un numero compreso tra 1 e 100.  <br/> |
   
## <a name="for-more-information"></a>Ulteriori informazioni

[Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md)
  
[Eseguire una ricerca contenuto nel centro sicurezza &amp; e conformità di Office 365](run-a-content-search-in-the-security-and-compliance-center.md)
  
[Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
  

