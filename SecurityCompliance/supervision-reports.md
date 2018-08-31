---
title: Rapporti di supervisione
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: Utilizzare rapporti di supervisione per visualizzare i messaggi di posta elettronica necessario esaminare la conformità e che devono eseguire.
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530398"
---
# <a name="supervision-reports"></a>Rapporti di supervisione

Definiscono criteri di supervisione cui communications all'interno dell'organizzazione devono revisione per la conformità e che verranno eseguite le valutazioni. Utilizzare i rapporti di supervisione esaminare l'attività di verifica a livello di criteri e revisore. Per ogni criterio, è inoltre possibile visualizzare le statistiche live sullo stato corrente dell'attività di verifica. [Ulteriori informazioni sui criteri di supervisione](configure-supervision-policies.md) . 
  
> [!NOTE]
> Utilizzo dei criteri di supervisione richiede una sottoscrizione a Office 365 E5 per l'organizzazione. Se non sono dial plan e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
È possibile utilizzare i rapporti di supervisione:
  
- Verificare che i criteri funzionino come previsto. 
    
- Scoprire quanti messaggi di posta elettronica viene identificati per la revisione.
    
- Scoprire quanti messaggi di posta elettronica non è conforme e quelli che stanno passando la revisione. Queste informazioni consentono di decidere se ottimizzare i criteri o modificare il numero di revisori.
    
## <a name="view-the-supervision-report"></a>Visualizzare il report di supervisione

1. Accedere al [protezione &amp; centro conformità](https://protection.office.com/) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365 con le autorizzazioni per visualizzare i report di supervisione.. 
    
2. Accedere a **rapporti** \> **Dashboard**. Verrà visualizzato un report widget per la supervisione e altri report è possibile accedere al.
    
3. Fare clic su widget **supervisione** per aprire la pagina report dettagliato. 
    
> [!NOTE]
> Se non si è in grado di accedere alla pagina di **report** , verificare che l'utente sia un membro del gruppo di ruoli revisione supervisione come illustrato in [rendere supervisione disponibili nell'organizzazione](configure-supervision-policies.md#SRavailable). L'inclusione nel consente di gruppo ruolo creare e gestire supervisione criteri ed eseguire il report. 
  
## <a name="how-to-use-the-report"></a>Come utilizzare i report

Quando un criterio di supervisione identifica un messaggio di posta elettronica per la revisione, il messaggio di posta elettronica viene recapitato nella cartella di supervisione del revisore in Outlook e Outlook web app. In questo report sono elencati il nome di ogni criterio e il numero delle comunicazioni in ogni fase del processo di revisione.
  
Utilizzare il report per:
  
- Visualizzare i dati per tutti i criteri specifici o.
    
- Visualizzare i dati raggruppati per tipo di tag (ad esempio conforme, Questionable e così via), revisore o tipo di messaggio.
    
- Esportare dati in un file CSV.
    
- Filtrare i dati in base a rivedere data dell'attività, tipo di tag, revisore, tipo di messaggio.
    
Di seguito vengono illustrati i valori che potrebbe essere presente nella colonna **tipo di Tag** . 
  
|**Tipo di tag**|**Significato**|
|:-----|:-----|
|Non è stato rivisto  <br/> |Il numero di messaggi di posta elettronica non ancora riviste. Questi messaggi di posta elettronica sono in attesa di revisione nella cartella di supervisione del revisore di Outlook.  <br/> |
|Compatible  <br/> |Il numero di messaggi di posta elettronica esaminato e contrassegnato come compatibile. Non è necessaria alcuna operazione.  <br/> |
|Ambigui  <br/> |Il numero di messaggi di posta elettronica esaminato e contrassegnati ambigui. Questo funge da un contrassegno; altri revisori consentono di controllare se un messaggio di posta elettronica deve indagini per motivi di conformità.  <br/> |
|Non conforme (attivo)  <br/> |Il numero di messaggi di posta elettronica non conforme che sono attualmente analisi dei revisori.  <br/> |
|Non è compatibile (risolti)  <br/> |Il numero di messaggi di posta elettronica non compatibili con i revisori esaminate e risolti.  <br/> |
   
## <a name="more-details"></a>Ulteriori informazioni

- Criteri di supervisione devono innanzitutto effettuare il provisioning prima che verranno visualizzate nel report.
    
- Se vengono eliminati i criteri, i dati cronologici viene ancora visualizzati. Tuttavia, viene indicati come "criterio inesistente" e la funzione di **esportazione** non è disponibile. 
    
- Se il report non è presente alcun dato per impostazione predefinita, potrebbe essere perché l'intervallo di date corrente non contiene dati da visualizzare. In questi casi, utilizzare il controllo di **filtri** per modificare l'intervallo di date. 
    

