---
title: Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Informazioni su come utilizzare la protezione di Office 365 &amp; centro conformità per accedere a Office 365 avanzate eDiscovery ed eseguire il modulo di processo per un caso.  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530811"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>Eseguire il modulo di processo e caricare i dati in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questa sezione viene descritta la funzionalità del modulo del processo eDiscovery avanzate. 
  
Oltre ai dati dei file, metadati, ad esempio tipo di file, estensione, posizione o percorso, la data di creazione e ora, autore, depositaria e argomento, è possibile caricare in avanzate eDiscovery e salvata per ciascun caso. Alcuni metadati viene calcolato dal eDiscovery avanzate, ad esempio, quando vengono caricati file nativi. 
  
EDiscovery avanzate fornisce sistema i valori dei metadati, ad esempio raggruppamenti quasi duplicati o punteggio di pertinenza. È possibile aggiungere altri metadati, ad esempio le annotazioni di file, l'amministratore. 
  
## <a name="running-process"></a>Processo in esecuzione

> [!NOTE]
> I numeri batch sono assegnati a un file nel corso per consentire la registrazione dei file. Il numero di batch consente inoltre l'identificazione dei processi batch per le opzioni di rielaborazione. Filtri aggiuntivi sono disponibili per il filtro per le sessioni e il numero di batch. 
  
Eseguire la procedura seguente per eseguire il processo.
  
1. [Aprire la protezione di Office 365 &amp; centro conformità](go-to-the-securitycompliance-center.md) . 
    
2. Accedere a **ricerca &amp; indagini** \> **eDiscovery** e quindi fare clic su **Vai a eDiscovery avanzate**.
    
3. In eDiscovery avanzate, selezionare il caso appropriato nella pagina visualizzata **casi** e fare clic su **Vai a caso**.
    
4. In **Prepara** \> **processo** \> **il programma di installazione**, selezionare un contenitore dall'elenco dei contenitori disponibili.
    
    ![Fare clic su processo per aggiungere i risultati di ricerca al caso](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Se si desidera aggiungere il contenitore come file di seeding o file pre-contrassegnati, fare clic su **Impostazioni avanzate** . 
    
    Seeding i file utilizzati per velocizzare la formazione per i problemi con complessità bassa (in genere 2%, massimo). Per i file di seeding, è consigliabile selezionare l'unità relativi file ed elaborare su 20-50 semi per ogni problema (Troppi file seeding possono variare i risultati di pertinenza). Dalla stessa persona verrà formare il problema, è consigliabile leggere i file di seeding.
    
    Utilizzare i file di pre-contrassegnati per automatizzare la formazione di pertinenza. Contrassegnare i file di almeno 1.500 e mantenere la proporzione di interesse per i file non rilevanti corrispondono a quelli insieme aggiunti alla pertinenza. Questi file devono essere contrassegnati manualmente, e devono essere certi della qualità del contrassegno.
    
    ![Cattura di schermata di avanzate della pagina Impostazioni per l'elaborazione in batch i file](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - Nella sezione **seeding** : 
    
    Scegliere **Contrassegna come file di seeding** per contrassegnare il contenitore come file di seeding. È inoltre necessario scegliere assegnarli al problema da **per problema di** elenco a discesa. Scegliere **relativo** o **non rilevanti** dall'elenco a discesa **Tag** . 
    
    > [!NOTE]
    > Dopo aver impostato i file come **seeding**, è possibile contrassegnare come **pre-contrassegnati**. 
  
  - Nella sezione **file pre-tag** : 
    
    Scegliere **Contrassegna come file pre-contrassegnati** per contrassegnare il contenitore come file pre-contrassegnati. È inoltre necessario assegnarli al problema da **per problema di** elenco a discesa. Scegliere **relativo** o **non rilevanti** dall'elenco a discesa **Tag** . 
    
    > [!NOTE]
    > Dopo aver impostato i file come **pre-contrassegnati**, è possibile contrassegnare come **seeding**. 
  
  - Nella sezione **posta elettronica tagging** . insieme quale parte di un messaggio di posta elettronica elaborato devono essere contrassegnati come router di inizializzazione o pre-contrassegnati. 
    
6. Per iniziare, fare clic su **processo**. Al termine, vengono visualizzati i risultati di processo.
    
7. (Facoltativo) Se si desidera assegnare le origini dati a un depositaria specifico, è possibile aggiungere e modificare i nomi depositaria in **depositari** \> **Gestisci** e assegna depositari in **depositari** \> **assegnare**. 
    
Se si aggiunge il caso, quindi è possibile elaborare nuovamente.
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Visualizzazione dei risultati modulo processo](view-process-module-results-in-advanced-ediscovery.md)

