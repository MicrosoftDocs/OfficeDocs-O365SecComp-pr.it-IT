---
title: Creare un tipo di informazione riservata personalizzato
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Scoprire come creare, modificare, rimuovere e testare tipi di informazioni sensibili personalizzati per la prevenzione della perdita dei dati (DLP) nell'interfaccia utente grafica nel Centro sicurezza e conformità di Office 365.
ms.openlocfilehash: cd7041ee9c20038fb7cb0c337f31d7cef7f7192d
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857294"
---
# <a name="create-a-custom-sensitive-information-type"></a>Creare un tipo di informazioni sensibili personalizzato

Prevenzione perdita dati (DLP) in Office 365 include molti [tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md) già pronte per l'uso nei criteri di protezione della perdita dei dati. Tali tipi integrati possono aiutare a identificare e proteggere i numeri di carte di credito, di conti bancari, di passaporto e molti altri. 

Tuttavia, se è necessario identificare e proteggere un tipo diverso di informazioni sensibili (ad esempio gli ID dipendente o i numeri di progetto che usano un formato specifico dell'organizzazione), è possibile creare un tipo di informazioni sensibili personalizzato.

Le parti fondamentali di un tipo di informazioni sensibili personalizzato sono:

- **Criterio principale**: ID dipendente, numeri di progetto e così via. In genere è identificato da un'espressione regolare (RegEx), ma può anche essere un elenco di parole chiave.

- **Evidenza aggiuntiva**: si supponga di cercare un numero ID dipendente di nove cifre. Non tutti i numeri di nove cifre sono numeri ID dipendente, quindi è possibile cercare testo aggiuntivo: parole chiave come "dipendente", "badge", "ID" o altri criteri di testo basati su ulteriori espressioni regolari. Questa evidenza di supporto (denominata anche evidenza__ _corroborativa_) consente di aumentare la probabilità che il numero di nove cifre individuato nel contenuto sia davvero un numero ID dipendente.

- **Prossimità dei caratteri**: è logico che più il criterio principale e l'evidenza di supporto sono vicini tra loro, più è probabile che il contenuto rilevato sia quello che si sta cercando. È possibile specificare la distanza dei caratteri tra il criterio principale e l'evidenza di supporto (nota anche come _finestra di prossimità_) come mostrato nel diagramma seguente:

    ![Diagramma dell'evidenza corroborativa e della finestra di prossimità](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Livello di probabilità**: più evidenze di supporto si hanno, più alta è la probabilità che una corrispondenza contenga le informazioni sensibili che si stanno cercando. È possibile assegnare livelli di probabilità più elevati per le corrispondenze rilevate con altre evidenze.

  Quando viene soddisfatto, un criterio restituisce un numero e un livello di probabilità che è possibile utilizzare nelle condizioni nei criteri DLP. Quando si aggiunge una condizione per il rilevamento di un tipo di informazione riservata a un criterio DLP, è possibile modificare il numero e il livello di probabilità, come illustrato nel diagramma seguente:

    ![Numero di istanze e opzioni di precisione di corrispondenza](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

Per creare tipi di informazioni riservate personalizzati nel Centro sicurezza e conformità di Office 365, si hanno le opzioni seguenti:

- **Usare l'interfaccia utente**: questo metodo è più facile e veloce, ma fornisce meno opzioni di configurazione rispetto a PowerShell. Il resto di questo argomento descrive tali procedure.

- **Usare PowerShell**: questo metodo richiede di creare prima un file XML (denominato _pacchetto di regole_) che contiene uno o più tipi di informazioni sensibili, quindi usare PowerShell per importare il pacchetto di regole (l'importazione del pacchetto di regole è semplicissima rispetto alla creazione del pacchetto di regole). Questo metodo è molto più complesso dell'interfaccia utente, ma fornisce un maggior numero di opzioni di configurazione. Per istruzioni in merito, vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità di Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md).

Le differenze principali vengono descritte nella tabella seguente:

|Tipi di informazioni sensibili personalizzati nell'interfaccia utente|Tipi di informazioni sensibili personalizzati in PowerShell|
|:-----|:-----|
|Nome e descrizione sono in una lingua.|Supporta più lingue per nome e descrizione.|
|Supporta un criterio (il criterio principale).|Supporta più criteri oltre al criterio principale.|
|Le evidenze di supporto possono essere: <br/>• Espressioni regolari <br/>• Parole chiave <br/>• Parole chiave personalizzate|Le evidenze di supporto possono essere: <br/>• Espressioni regolari <br/>• Parole chiave <br/>• Parole chiave personalizzate <br/>• [Funzioni di prevenzione della perdita dei dati incorporate](what-the-dlp-functions-look-for.md)|
|Il livello di probabilità è configurabile per il tipo di informazioni sensibili.|Il livello di probabilità è configurabile per il tipo di informazioni sensibili e per ogni singolo criterio all'interno.|
|La corrispondenza al criterio richiede il rilevamento del criterio principale e di tutte le evidenze di supporto (viene usato l'operatore AND implicito).|La corrispondenza al criterio richiede il rilevamento del criterio principale e di una quantità configurabile di evidenze di supporto (vengono usati gli operatori AND e OR impliciti).|

## <a name="what-do-you-need-to-know-before-you-begin"></a>Informazioni preliminari

- Per aprire il Centro sicurezza e conformità, vedere [Accedere al Centro sicurezza e conformità di Office 365](go-to-the-securitycompliance-center.md).

- I tipi di informazioni sensibili personalizzati richiedono una certa familiarità con le espressioni regolari (RegEx). Per ulteriori informazioni sul motore RegEx .NET utilizzato per l'elaborazione del testo, vedere [Espressioni regolari .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).

  Il Supporto tecnico Microsoft non può dare assistenza nella fornitura di definizioni di corrispondenza del contenuto personalizzate (definizione di classificazioni personalizzate o criteri di espressioni regolari). I tecnici del supporto possono fornire supporto limitato per la funzionalità, ma non possono garantire che qualsiasi sviluppo personalizzato di corrispondenza del contenuto soddisfi i requisiti o gli obblighi del cliente. Come esempio del tipo di supporto che può essere fornito, è possibile fornire esempi di modelli di espressioni regolari a scopo di test. In alternativa, il supporto può aiutare nella risoluzione dei problemi di un criterio RegEx esistente che non si attiva come previsto.

- Per ulteriori informazioni sul motore RegEx .NET utilizzato per l'elaborazione del testo, vedere [Espressioni regolari in .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).

- DLP usa il crawler di ricerca per identificare e classificare le informazioni sensibili nei siti di SharePoint Online e OneDrive for Business. Per identificare il nuovo tipo di informazioni sensibili personalizzato nel contenuto esistente, è necessario che venga effettuata una nuova ricerca per indicizzazione. Il contenuto viene sottoposto nuovamente alla ricerca in base a una programmazione, ma è possibile effettuare manualmente la ricerca per indicizzazione per una raccolta siti, un elenco o una raccolta. Per ulteriori informazioni, vedere [Richiedere manualmente l'esecuzione di una nuova ricerca per indicizzazione e la reindicizzazione di un sito, una raccolta o un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content).

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità

Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.

Le impostazioni sono abbastanza chiare e vengono spiegate nella pagina della procedura guidata associata:

- **Nome**

- **Descrizione**

- **Prossimità**

- **Livello di probabilità**

- **Elemento pattern principale** (parole chiave, espressione regolare o dizionario)

- Facoltativo **Elementi pattern di supporto** (parole chiave, espressione regolare o dizionario) e un valore di **costo minimo** corrispondente.

Ecco uno scenario: si desidera un tipo di informazioni sensibili personalizzato che rilevi i numeri dipendente di 9 cifre nel contenuto, con le parole chiave "dipendente", "ID" e "badge". Per creare un tipo di informazioni sensibili personalizzato, procedere come segue:

1. Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.

2. Nella pagina **Scegliere un nome e una descrizione** che viene visualizzata, immettere i valori seguenti:

  - **Nome**: ID dipendente.

  - **Descrizione**: Rilevare i numeri ID dipendente di Contoso di 9 cifre.

  Al termine dell'operazione, fare clic su **Avanti**.

3. Nella pagina **Requisiti per la corrispondenza** che viene visualizzata, fare clic su **Aggiungi un elemento** e configurare le impostazioni seguenti:

  - **Rilevare il contenuto che contiene**:
 
    a. Fare clic su **Una qualsiasi di queste condizioni** e selezionare **Espressione regolare**.

    b. Nella casella di espressione regolare, immettere `(\s)(\d{9})(\s)` (numeri di 9 cifre racchiusi da spazi).
  
  - **Elementi di supporto**: fare clic su **Aggiungi gli elementi di supporto** e selezionare **Contiene questo elenco di parole chiave**.

  - Nell'area **Contiene questo elenco di parole chiave** che viene visualizzata, configurare le impostazioni seguenti:

    - **Elenco di parole chiave**: immettere il valore seguente: dipendente,ID,badge.

    - **Numero minimo**: lasciare il valore predefinito 1.

  - Lasciare il valore 60 del **Livello di probabilità** predefinito. 

  - Lasciare il valore 300 della **Prossimità dei caratteri** predefinito.

  Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Verifica e completamento** che viene visualizzata, controllare le impostazioni e fare clic su **Fine**.

5. La pagina successiva invita a testare il nuovo tipo di informazioni sensibili personalizzato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center). In alternativa, fare clic su **Annulla**.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che sia stato creato correttamente un nuovo tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:

  - Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e verificare che sia presente il nuovo tipo di informazioni sensibili personalizzato.

  - Testare il nuovo tipo di informazioni sensibili personalizzato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>Modificare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità

**Nota**: è possibile modificare solo i tipi di informazioni sensibili personalizzati; non è possibile modificare quelli predefiniti. Tuttavia, è possibile usare PowerShell per esportare i tipi di informazioni sensibili personalizzati predefiniti, personalizzarli e importarli come tipi di informazioni sensibili personalizzati. Per ulteriori informazioni, vedere [Personalizzare un tipo di informazioni sensibili predefinito](customize-a-built-in-sensitive-information-type.md).

Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e selezionare il tipo di informazioni sensibili personalizzato da modificare.

Le stesse opzioni sono disponibili qui come quando è stato creato il tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#create-custom-sensitive-information-types-in-the-security--compliance-center).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che sia stato modificato correttamente un tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:

  - Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare le proprietà del tipo di informazioni sensibili personalizzato modificato.

  - Testare il tipo di informazioni sensibili personalizzato modificato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>Rimuovere tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità 

**Note**:

- È possibile rimuovere i tipi di informazioni sensibili personalizzati; non è possibile rimuovere quelli predefiniti.

- Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.

1. Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e selezionare uno o più tipi di informazioni sensibili personalizzati da rimuovere.

2. Nel menu a comparsa che viene visualizzato, fare clic su **Elimina** (o **Eliminare i tipi di informazioni sensibili** se ne sono stati selezionati più di uno).

3. Nel messaggio di avviso che viene visualizzato, fare clic su **Sì**.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per accertarsi di aver rimosso correttamente un tipo di informazioni sensibili personalizzato, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare che il tipo di informazioni sensibili personalizzato non sia più presente.


## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>Testare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità

1. Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**.

2. Selezionare uno o più tipi di informazioni sensibili personalizzati da testare. Nel menu a comparsa che viene visualizzato, fare clic su **Tipo di test** (o **Test dei tipi di informazioni sensibili** se ne sono stati selezionati più di uno).

3. Nella pagina che viene visualizzata, caricare un documento per il test trascinando e rilasciando un file o facendo clic su **Sfoglia** e selezionando un file.

4. Fare clic sul pulsante **Test** per testare il documento per individuare le corrispondenze al criterio nel file.
