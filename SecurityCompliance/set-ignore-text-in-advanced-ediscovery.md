---
title: Impostare l’opzione Ignora messaggio per Analizza in Office 365 Advanced eDiscovery
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 'Informazioni su come definire la regola per ignorare il testo specificato quando si utilizzano i moduli di processo e analisi di Office 365 avanzate eDiscovery.  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530843"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>Impostare l’opzione Ignora messaggio per Analizza in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
La caratteristica Ignora testo può essere applicata a tutto o uno dei seguenti moduli avanzati eDiscovery: analizzare (quasi duplicati thread di posta elettronica, temi) e la pertinenza. Testo ignorato non verrà visualizzato nel file visualizzati in pertinenza e analisi/calcoli eliminerà il testo ignorato.
  
Se la caratteristica di ignorare il testo è stata definita in precedenza per i moduli che sono già stato eseguito, l'impostazione Ignora testo ora essere protetto dalle modifiche apportate. La caratteristica di ignorare il testo per il modulo di pertinenza può comunque essere modificata in qualsiasi momento.
  
## <a name="how-ignore-text-filters-are-applied"></a>Modalità di applicazione di filtri Ignora testo

Più filtri Ignora testo vengono applicati nell'ordine che sono stati immessi. Per modificare l'ordine in cui vengono applicati, devono essere eliminati e rientrati nell'ordine desiderato.
  
Se il contenuto del testo è ad esempio: "DAVE BOB ALICE CAROL Giudici", esempi di voci di Ignora testo e i risultati vengono riportati di seguito:
  
||||
|:-----|:-----|:-----|
|**Ignora le voci di testo** <br/> |**==\>** <br/> |**Risultati** <br/> |
|"ALICE", "BOB ADRIANA"  <br/> |==\>  <br/> |"DAVE GIUDICI"  <br/> |
|"ALICE", "BOB ALICE CAROL"  <br/> |==\>  <br/> |"DAVE BOB CAROL GIUDICI"  <br/> |
   
La seconda voce Ignora testo non è implementata perché la stringa non viene trovata in quanto tale dopo il testo di ignorare la prima applicazione.
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>Utilizzare le espressioni regolari durante la definizione Ignora testo

Espressioni regolari sono supportate per l'utilizzo durante la definizione Ignora testo. Di seguito sono riportati esempi di utilizzo e la sintassi di espressione regolare:
  
- Per rimuovere (ignorare) testo iniziale fino alla fine di una riga:
    
     `Begin(.*)$`
    
    dove "Begin" è l'occorrenza iniziale di questa stringa nella riga.
    
    Ad esempio, per il testo seguente:
    
    **"This is prima frase e prima riga**
    
    **Si tratta seconda frase e seconda riga"**
    
    l'espressione regolare first(.\*) $ determinerà:
    
    **"Questa è**
    
    **Si tratta seconda frase e seconda riga"**
    
- Per rimuovere automaticamente inseriti alla fine di thread di posta elettronica informazioni legali e dichiarazioni di non responsabilità:
    
     `Begin(.|\s)*End`
    
    dove "Begin" e "End" sono stringhe univoche all'inizio e fine di un paragrafo di ritorno a capo automatico. 
    
    Ad esempio, l'espressione regolare rimuoverà dichiarazioni di non responsabilità e informazioni legali che sono stati in thread di posta elettronica tra le stringhe Begin ed End:
    
    **Il messaggio contiene informazioni riservate (. | \s)\*verifica è necessaria richiedere una versione cartacei**
    
- Per rimuovere una dichiarazione di non responsabilità (inclusi i caratteri speciali): 
    
    Ad esempio, per il testo seguente (con la dichiarazione di non responsabilità rappresentata da x): 
    
    **/\*\ Il messaggio contiene informazioni riservate. xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx se è necessario, la verifica Richiedi una versione di stampato. /\*\**
    
    l'espressione regolare per rimuovere la dichiarazione di non responsabilità precedente deve essere: 
    
    **\/\\*\\Il messaggio contiene informazioni riservate\.(. | \s)\* verifica è necessaria richiedere una versione cartacei\.\/\\*\\**
    
- Regole di espressione regolare:
    
  - Tutti i caratteri che non fanno parte dell'alfabeto ad eccezione di spazi da parte, "_" e "-" deve essere preceduto da "\".
    
  - Il campo eExpression regolare può essere un numero illimitato di lunghezza.
    
> [!TIP]
> Per una spiegazione e informazioni dettagliate sulla sintassi delle espressioni regolari, vedere: [Linguaggio di espressioni regolari - Guida di riferimento rapido](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx). 
  
## <a name="define-ignore-text-rule"></a>Definire la regola ignora testo

1. Nella **Gestisci \> Analizza \> analizzare le opzioni** fare clic su scheda, nella sezione **Ignora testo** il **+** icona per aggiungere una regola. 
    
2. Nella finestra di dialogo **Aggiungi Ignora testo** nel campo **nome** digitare un nome per la regola ignora testo. 
    
    ![Aggiungi testo ignorato](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. Nella casella di **testo** , digitare il testo verrà ignorato. Il campo testo consente a un numero illimitato di caratteri. 
    
    > [!TIP]
    > Come indicato nella precedente finestra, fare clic su **lampadina** per visualizzare le linee guida sintassi comuni per la regola ignora testo. 
  
4. Se lo si desidera, selezionare la casella di controllo **maiuscole/minuscole** . 
    
5. Nell'elenco **Applica a** selezionare moduli avanzati eDiscovery in cui si desidera applicare la definizione. 
    
6. Se si desidera che un'esecuzione di test in testo di esempio, digitare il testo di esempio nella casella di testo **Input** e fare clic su **Test**. I risultati vengono visualizzati nella casella di testo **Output** . 
    
7. Fare clic su **OK** per salvare la regola ignora testo. Viene visualizzata la regola ignora testo definita. 
    
    ![Impostare nome del testo ignorato](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sui similarità documento](understand-document-similarity-in-advanced-ediscovery.md)
  
[Impostazione delle opzioni di analisi](set-analyze-options-in-advanced-ediscovery.md)
  
[Impostazioni avanzate di analisi di impostazione](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualizzazione dei risultati di analisi](view-analyze-results-in-advanced-ediscovery.md)

