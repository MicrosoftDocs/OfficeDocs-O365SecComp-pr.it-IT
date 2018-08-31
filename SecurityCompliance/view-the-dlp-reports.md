---
title: Visualizzare i report di prevenzione della perdita di dati
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: Con i rapporti DLP in Office 365, è possibile visualizzare rapidamente il numero di corrispondenze di criteri DLP, sostituzioni o falsi positivi; Se si sta avvicinando verso l'alto o verso il basso nel tempo, vedere filtrare il report in vari modi; e visualizzare dettagli aggiuntivi selezionando un punto sulla linea nel grafico.
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013910"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Visualizzare i report di prevenzione della perdita di dati

Dopo aver creato la perdita di dati politiche di prevenzione (DLP), è consigliabile verificare che si sta lavorando come è lo scopo e servizio di supporto per garantire la conformità. Con il DLP report in Office 365 Security &amp; centro conformità, è possibile visualizzare rapidamente:
  
- **Corrispondenze criteri DLP** In questo rapporto viene visualizzato il numero di corrispondenze di criteri DLP nel tempo. È possibile filtrare il report per data, posizione, criteri o azione. È possibile utilizzare questo report per: 
    
  - Ottimizzare o filtrare i criteri DLP come eseguirli in modalità test. È possibile visualizzare la regola specifica corrispondenti al contenuto.
    
  - Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.
    
  - Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.
    
  - Acquisire familiarità con un impatto aziendale di criteri DLP visualizzando le azioni vengono applicate al contenuto.
    
  - Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.
    
  - Visualizzare un elenco degli utenti principali e ripetere gli utenti che contribuiscono a risolte all'interno dell'organizzazione.
    
  - Visualizzare un elenco dei tipi principali di informazioni riservate dell'organizzazione.
    
- **Risolte DLP** Questo report mostra inoltre corrispondenze di criteri nel tempo, come report genera una corrispondenza per i criteri. Tuttavia, il criterio corrisponde report mostra corrisponde a un livello di regola. Se, ad esempio, un messaggio di posta elettronica corrispondenti a tre regole diverse, il criterio corrisponde report mostra tre diverse voci. Al contrario, il rapporto risolte Mostra corrisponde a un livello di elemento; ad esempio, se un messaggio di posta elettronica corrispondenti a tre regole diverse, il rapporto risolte Mostra una singola voce di tale parte del contenuto. 
    
  Poiché i conteggi dei report è aggregati in modo diverso, il rapporto di corrispondenze di criteri è migliore per l'identificazione di corrispondenze con regole specifiche e regolazione criteri DLP. Il rapporto risolte è migliore per identificare le parti specifiche del contenuto sono problematiche per i criteri DLP.
    
- **Sostituzioni e falsi positivi DLP** Se il criterio DLP consente agli utenti di ignorare lo o un falso positivo, questo rapporto viene visualizzato un numero di istanze di questo tipo nel tempo. È possibile filtrare il report per data, posizione o criteri. È possibile utilizzare questo report per: 
    
  - Ottimizzare o filtrare i criteri DLP visualizzando i criteri comportano un numero elevato di falsi positivi.
    
  - Consente di visualizzare motivazioni inviate dagli utenti durante la risoluzione di un suggerimento criterio ignorando il criterio.
    
  - Scopri dove esegue l'override di conflitto di criteri DLP con i processi aziendali valido, poiché richiede un numero elevato di utenti.
    
Tutti i rapporti DLP possono visualizzare i dati del periodo di tempo quattro mesi più recente. I dati più recenti possono richiedere fino a 24 ore per visualizzati nei rapporti.
  
È possibile trovare questi rapporti in sicurezza &amp; centro conformità \> **report** \> **Dashboard**.
  
![Corrispondenze di criteri DLP report](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Consente di visualizzare la motivazione inviata da un utente per un override

Se il criterio DLP consente agli utenti di ignorare lo, è possibile utilizzare il falso positivo e sostituire report per visualizzare il testo inviato dagli utenti durante il suggerimento sul criterio.
  
![Campo giustificazione nei dettagli dei falsi positivi DLP e report di sostituzione](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Eseguire l'azione su informazioni e suggerimenti

È possibile report visualizzati sui concetti e i suggerimenti dove è possibile fare clic sull'icona di avviso rosso per visualizzare i dettagli sui possibili problemi ed eseguire azioni correttive possibili.
  
![Fare clic su un'icona informativa per visualizzare informazioni dettagliate e le azioni da eseguire](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Trovare i cmdlet per i rapporti DLP

Utilizzare la maggior parte dei cmdlet per la sicurezza &amp; centro conformità, è necessario:
  
1. [Connettersi a Office 365 Security &amp; centro conformità utilizzando PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Utilizzare una qualsiasi delle domande [protezione di Office 365 &amp; cmdlet centro conformità](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
Tuttavia, rapporti DLP necessario estrarre dati da tra Office 365, inclusi Exchange Online. Per questo motivo, i cmdlet per i rapporti DLP sono disponibili in Exchange Online Powershell, ovvero non in sicurezza &amp; Powershell centro conformità. Pertanto, per utilizzare i cmdlet per i rapporti DLP, è necessario:
  
1. [Connessione a Exchange Online tramite remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Utilizzare uno di questi cmdlet per i rapporti DLP:
    
      - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

