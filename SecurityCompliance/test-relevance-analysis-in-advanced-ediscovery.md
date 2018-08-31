---
title: Valutare l’analisi di Rilevanza in Office 365 Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: "Informazioni su come utilizzare la scheda Test dopo il calcolo Batch in Office 365 avanzate eDiscovery per testare, confronto e convalidare della qualità globale dell'elaborazione.  "
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530819"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a>Valutare l’analisi di Rilevanza in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Nella scheda Test di eDiscovery avanzate consente di testare, confronto e convalidare della qualità globale dell'elaborazione. Questi test vengono eseguiti dopo il calcolo Batch. Per contrassegno i file della raccolta, un esperto rende la decisione finale se tutti i file contrassegnati viene effettivamente rilevanti per il case. 
  
Negli scenari con uno o più problemi test sono in genere eseguito per ogni problema. I risultati possono essere visualizzati dopo ogni test e i risultati dei test può essere adattati con i file di test di esempio specificato.
  
## <a name="testing-the-rest"></a>Nella parte restante di test

Il test "Testare il resto" viene utilizzato per convalidare le decisioni eliminazione selettiva, ad esempio, per esaminare solo file sopra un punteggio limito di pertinenza specifico in base ai risultati finali eDiscovery avanzate. Esperto illustra un esempio di file in un punteggio limito selezionato calcolare il numero di file pertinenti all'interno di tale set.
  
Questo test vengono fornite le statistiche e un confronto tra il set di revisione e il Test della popolazione Rest. I risultati del set di revisione sono quelli calcolati per pertinenza durante la formazione. I risultati includono calcoli, in base alle impostazioni e i parametri di input, ad esempio:
  
- Testare le statistiche di esempio il numero di file in un file pertinente di esempio e identificati. 
    
- Confronto tra tabulare dei parametri popolazione del set di revisione e gli altri componenti, ad esempio, il numero di file, numero stimato di file rilevanti, complessità stimato e il costo medio di ricerca di un altro file pertinente. Costi parametro impostazioni possono essere configurate dall'amministratore.
    
1. Apri il **pertinenza \> Test** scheda. 
    
2. Nella scheda **Test** , fare clic su **Nuovo test**. Verrà visualizzata la finestra di dialogo **Crea di test** , come illustrato nell'esempio seguente. 
    
    ![Risultati del test sull'inattività di pertinenza](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. In **nome Test**e **Descrizione**digitare il nome e descrizione.
    
4. Nell'elenco **tipo di Test** , selezionare **Test il resto**
    
5. Nella **problema / categoria** , selezionare il nome del problema. 
    
6. Nell'elenco **caricare** selezionare il carico. 
    
7. In **% lettura**, accettare il valore predefinito oppure selezionare un valore per il limite punteggio di pertinenza. 
    
8. **Impostare dimensioni**, oppure accettare il valore predefinito. Si noti che le icone di ripristino è possibile ripristinare i valori predefiniti.
    
9. Fare clic su **Start tagging**. Viene generato un campione.
    
10. Rivedere e contrassegnare ciascuno dei file nel **pertinenza \> Tag** delle schede e al termine, fare clic su **calcolo**.
    
11. Nella scheda Test è possibile scegliere di **visualizzare i risultati** per visualizzare i risultati del test. Nella figura seguente è illustrato un esempio. 
    
    ![Risultati del test sull'inattività](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Nella figura precedente, la sezione **esempi di parametri** della tabella contiene informazioni dettagliate sul numero di file di esempio contrassegnato da un esperto e il numero di file rilevanti trovato nel modello di tale. 
  
La sezione **parametri popolazione** della tabella contiene i risultati del test, inclusi la compilazione di set di verifica dei file con un punteggio sotto il limite selezionato e popolazione "Il resto" dei file con un punteggio sopra il limite selezionato. Per ogni popolazione, vengono visualizzati i risultati seguenti: 
  
- Include i file con % lettura - limite già indicati
    
- Il numero totale di file 
    
- Il numero stimato di file rilevanti 
    
- Complessità stimato 
    
- Il costo medio revisione della ricerca di un altro file rilevante
    
## <a name="testing-the-slice"></a>La parte del test

"Testare la sezione" test consente di eseguire test simili a "Testare il resto" test, ma a un segmento del file impostata secondo quanto specificato % lettura di pertinenza.
  
1. Apri il **pertinenza \> Test** scheda. 
    
2. Nella scheda **Test** , fare clic su **Nuovo test**. Viene visualizzata la finestra di dialogo **Crea di test** . 
    
3. In **nome Test** e **Descrizione**digitare le informazioni.
    
4. Nell'elenco **tipo di Test** , selezionare **la parte del Test**.
    
5. Nell'elenco **problema** , selezionare il nome del problema. 
    
6. Nell'elenco **caricare** selezionare il carico. 
    
7. Nella finestra **% lettura tra**, accettare i valori predefiniti intervallo massimo e minimo o selezionare i valori per i punteggi pertinenza limiti. 
    
8. **Impostare dimensioni**, selezionare un valore o accettare il valore predefinito.
    
    Il valore predefinito è possibile ripristinare le icone di ripristino.
    
9. Fare clic su **Start tagging**. Viene generato un campione.
    
10. Rivedere e contrassegnare ciascuno dei file nel **pertinenza \> Tag** delle schede e al termine, fare clic su **calcolo**. 
    
11. Nella scheda Test è possibile scegliere di **visualizzare i risultati** per visualizzare i risultati del test. 
    
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Informazioni sulla valutazione di pertinenza](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging e formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analisi di pertinenza di verifica](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Stabilire in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)

