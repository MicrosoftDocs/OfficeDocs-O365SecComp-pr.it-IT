---
title: Visualizzare le opzioni di Analizza in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Rivedere i passaggi per impostare le opzioni per il processo di analisi di eDiscovery Office 365 avanzate, tra cui quasi duplicati, thread di posta elettronica e temi.  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530791"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a>Visualizzare le opzioni di Analizza in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Nella scheda Avanzate eDiscovery, impostare le opzioni di analisi prima dell'esecuzione di analisi.
  
## <a name="set-analyze-options"></a>Impostare le opzioni di analisi

Apri **preparare \> analizzare** \> **il programma di installazione**. Verrà visualizzata la finestra seguente.
  
![Impostare opzioni di analisi](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **Quasi duplicati e thread di posta elettronica** Selezionare questa casella se si desidera eseguire l'analisi. È selezionata per impostazione predefinita. 
  
 **Similarità documento** Immettere il valore di soglia Near duplicati o accettare il valore predefinito è 65%. 
  
 **Temi** Selezionare questa casella per elaborare tutti i file e assegnare loro temi. Per impostazione predefinita, questa casella di controllo non è selezionata. Se si desidera eseguire temi di elaborazione, immettere le opzioni seguenti.
  
- **Numero massimo di temi** Immettere o selezionare un valore per il numero di temi per creare. Il valore predefinito è 200. 
    
    > [!NOTE]
    > L'aumento del numero di temi influisce sulle prestazioni, nonché la possibilità di un tema per generalizzare. Maggiore è il numero di temi, più granulare sono. Se, ad esempio, un insieme di 50 temi includa un tema, ad esempio "Pallacanestro, tramite il, elettrico, Lakers"; 300 temi possono includere i temi separati: "Tramite il", "E", "Lakers". Se si non consapevolezza del tema "Pallacanestro" e utilizzare questa caratteristica per ECA, visualizzando il tema "Pallacanestro" può essere utile. Tuttavia, se l'elaborazione hanno un numero eccessivo di temi, che non venga visualizzato la parola "Pallacanestro" e non possono essere noti che tramite il ed elettrico è buone temi pallacanestro per esaminare, anziché gli elementi da inserire nel viene avviato e utilizzato per fini. 
  
- **Temi suggeriti** È inoltre possibile indicare parole tema per controllare l'elaborazione di temi. EDiscovery avanzate verrà occuparsi di queste parole suggerite e tenta di creare uno o più temi rilevanti, in base alle impostazioni "Max numero di temi". 
    
    Ad esempio, se la parola consigliata è "computer" e specificato "2" come "numero massimo di temi", eDiscovery avanzate tenterà di generare due temi correlate alla parola "computer". Due temi potrebbero essere "computer" hardware e "software", ad esempio. 
    
    ![Aggiungi tema suggerito](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. Per visualizzare, aggiungere o modificare i temi consigliati, fare clic su **Modifica**.
    
2. Nel Pannello di **temi suggeriti** , fare clic su **Aggiungi**![aggiungere icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icona per aggiungere un tema. Nel Pannello di **tema suggerita Add** , aggiungere le parole, separate da virgole. 
    
3. Nella casella **numero di temi**di selezionare un valore per determinare il numero di temi avanzate eDiscovery cercherà di generare per queste parole (valore predefinito è 1 tema).
    
4. Fare clic su **Salva** e quindi chiudere la finestra di dialogo. 
    
    > [!NOTE]
    > Il numero totale di temi include temi suggerito. I temi suggerito totale non può superare i temi totali. Se sono presenti molti temi suggerito rispetto al totali temi, solo alcuni temi "quesiti nuovi" vengono rilevati dal sistema in quanto la maggior parte dei temi dovrà essere dedicata ai temi suggerito. 
  
- **Modalità** Dall'elenco a discesa selezionare un'opzione di **temi** : 
    
  - **Creare e applicare modelli**: calcola temi dai modelli da un segmento dei file e quindi distribuisce i file tra loro.
    
  - **Crea modello**: calcola un modello di temi di un segmento dei file. Il processo di applica della divisione di file è terminato separatamente in un secondo momento.
    
  - **Applica modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non ancora applicato. Ciò consente di dividere il file in base ai temi.
    
È inoltre possibile [set Ignora testo](set-ignore-text-in-advanced-ediscovery.md) e [impostare analizza le impostazioni avanzata](set-analyze-advanced-settings-in-advanced-ediscovery.md) di analisi. 
  
Dopo aver impostato queste opzioni, fare clic su **analisi** per l'esecuzione. [Visualizzazione analizzare i risultati](view-analyze-results-in-advanced-ediscovery.md) vengono visualizzati. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sui similarità documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Impostare Ignora testo](set-ignore-text-in-advanced-ediscovery.md)
  
[Impostazioni avanzate per l'analisi](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualizzare i risultati di analisi](view-analyze-results-in-advanced-ediscovery.md)

