---
title: Prepara i dati per Office 365 Advanced eDiscovery
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: "Informazioni su come utilizzare la protezione di Office 365 &amp; centro conformità per preparare i dati di Office 365 per l'analisi con Office 365 avanzate eDiscovery. "
ms.openlocfilehash: cf0c76b0c274121da435de7829c769abf5111cab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531194"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>Prepara i dati per Office 365 Advanced eDiscovery

In questo argomento viene illustrato come caricare i risultati di una ricerca nel contenuto a un caso di eDiscovery avanzate. 
  
> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>Passaggio 1: Preparare i dati di Office 365 per eDiscovery avanzate

Per analizzare i dati con eDiscovery avanzate, è possibile utilizzare i risultati di ricerca di contenuto che viene eseguito in Office 365 Security &amp; centro conformità (elencata nella pagina di **ricerca del contenuto** in Office 365 Security &amp; centro conformità) o una ricerca associata a un caso di eDiscovery (elencata nella pagina di **eDiscovery** in sicurezza &amp; centro conformità). 
  
Per informazioni dettagliate sulla preparazione dei risultati di ricerca per l'analisi di eDiscovery avanzate, vedere [Prepare i risultati della ricerca eDiscovery avanzate di Office 365](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Se si dispone di dati all'esterno di Office 365 e da importare a Office 365 in modo che sia possibile preparare e analisi di eDiscovery avanzate, vedere [Panoramica di importazione del file PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) e [archiviazione dei dati di terze parti in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918). 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Passaggio 2: Carico il risultato della ricerca in caso di eDiscovery avanzate

Dopo aver preparato i risultati della ricerca per la protezione &amp; centro conformità per l'analisi, il passaggio successivo consiste nel caricare i risultati della ricerca in caso di eDiscovery avanzate. Per ulteriori informazioni, vedere [eseguire la funzionalità di processo](run-the-process-module-in-advanced-ediscovery.md).
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. In sicurezza &amp; centro conformità, fare clic su **ricerca &amp; indagini** \> **eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione. 
    
4. Accanto al caso in cui si desidera caricare i dati di eDiscovery avanzate fare clic su **Apri** . 
    
5. Nella Home **page per il case,** fare clic su **Avanzate eDiscovery**. 
    
    ![Fare clic su passa a eDiscovery avanzate per aprire il caso di eDiscovery avanzate](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Viene visualizzato l'indicatore di stato di **connessione avanzate eDiscovery** . Quando si è connessi a eDiscovery avanzate, viene visualizzato un elenco dei contenitori nella pagina installazione per il case. 
    
    ![Viene visualizzato il caso di eDiscovery avanzate](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi di eDiscovery avanzata nel passaggio 1. Si noti che il nome del contenitore ha lo stesso nome di ricerca del contenuto nel caso della protezione &amp; centro conformità. I contenitori nell'elenco sono quelli preparato. Se un utente diverso preparato risultati della ricerca eDiscovery avanzate, i contenitori corrispondenti non vengono inclusi nell'elenco. 
    
6. Per caricare i dati dei risultati di ricerca da un contenitore in caso di eDiscovery avanzate, selezionare un contenitore e quindi fare clic su **processo**.
    
Dopo avere i risultati di ricerca della protezione &amp; centro conformità vengono aggiunti al caso di eDiscovery avanzate, il passaggio successivo consiste nell'utilizzare gli strumenti di eDiscovery avanzate per analizzare e riforma i dati che riguardano il caso. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Configurare gli utenti e dei casi](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analisi dei dati maiuscole](analyze-case-data-with-advanced-ediscovery.md)
  
[Gestione dell'installazione di pertinenza](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Utilizzo del modulo di pertinenza](use-relevance-in-advanced-ediscovery.md)
  
[Esportazione dei dati di maiuscole](export-case-data-in-advanced-ediscovery.md)

