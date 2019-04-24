---
title: Gestire le notifiche di blocco
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fa83a90448250a91d6c2ccbf43588ee18e00619c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241263"
---
# <a name="manage-hold-notifications"></a>Gestire le notifiche di blocco

Dopo aver avviato il flusso di lavoro di notifica per la conservazione legale, è possibile sfruttare Advanced eDiscovery (Preview) per monitorare lo stato delle comunicazioni. La scheda comunicazioni Mostra tutte le notifiche di blocco all'interno del caso Advanced eDiscovery (Preview). In questa sezione, è possibile visualizzare i dettagli, ad esempio il numero di depositari che sono stati assegnati o che hanno riconosciuto l'avviso.

## <a name="view-communication-details"></a>Visualizzare i dettagli della comunicazione

### <a name="track-acknowledgements"></a>Conferma del rilevamento

Dopo aver selezionato una comunicazione dalla scheda **comunicazioni**, è possibile visualizzare un elenco di depositari che hanno riconosciuto un avviso di esenzione. 

### <a name="preview-acknowledgements"></a>Ringraziamenti per l'anteprima

Nel riquadro a comparsa dettagli comunicazione, è possibile visualizzare in anteprima i dettagli relativi alla comunicazione per il blocco legale. Nel riquadro di **Anteprima** , sarà possibile visualizzare un'istantanea rapida della notifica di conservazione legale, nonché le impostazioni e il contenuto delle notifiche del flusso di lavoro. Nel riquadro di anteprima verranno inoltre riportate le informazioni relative ai depositari che hanno già riconosciuto la notifica.

## <a name="taking-action-on-existing-communications"></a>Esecuzione di un'azione sulle comunicazioni esistenti

### <a name="re-send-a-hold-notice"></a>Inviare di nuovo un avviso di esenzione

Occasionalmente, i depositari perdono il controllo dei messaggi di posta elettronica nel lavoro quotidiano. In alternativa, per un contenzioso di lunga durata, un custode può raggiungere e chiedere di inviare di nuovo un avviso. Durante la gestione del flusso di lavoro per gli avvisi relativi alla conservazione legale, potrebbe essere necessario inviare di nuovo una notifica per riportarla nella "parte superiore della cassetta postale di un utente".

È possibile inviare di nuovo un avviso di conservazione al proprio custode:
1. Passare a un caso all'interno di **sicurezza e conformità _GT_ Advanced eDiscovery (Preview)**.
2. Dopo aver selezionato un caso, passare alla scheda **comunicazioni** .
3. Per inviare di nuovo un avviso per la conservazione legale a un custode, selezionare la comunicazione e fare clic sull'opzione di **nuovo invio** .
4. Se un custode non ha già riconosciuto la notifica di blocco, il flusso di sollecito e di escalation verrà riavviato. Se un custode ha già riconosciuto la notifica di conservazione, il custode riceverà solo una copia dell'avviso di conservazione iniziale.

> [!NOTE]
> È possibile inviare di nuovo solo una notifica di blocco legale ai depositari che sono assegnati alla comunicazione. 

### <a name="edit-a-communication"></a>Modificare una comunicazione

#### <a name="update-preservation-requirements"></a>Aggiornare i requisiti di conservazione
  
Quando il caso progredisce, potrebbe essere necessario che i depositari possano conservare dati aggiuntivi o meno rispetto a quelli precedentemente istruiti. In termini di eDiscovery, è necessario riemettere la notifica di conservazione con il contenuto aggiornato.

Per aggiornare il contenuto dell'avviso di blocco iniziale:

1. Passare a un caso all'interno di **sicurezza e conformità _GT_ Advanced eDiscovery (Preview)**.
2. Dopo aver selezionato un caso, passare alla scheda **comunicazioni** .
3. Selezionare l'avviso di blocco che si desidera aggiornare e fare clic su **modifica**.
4. Nel flusso di lavoro modifica, selezionare **Definisci contenuto portale** e aggiornare il contenuto della notifica. 
5. Fare clic su **Salva**. Una volta salvata, l'avviso di riemissione verrà inviato a tutti i depositari attualmente assegnati alla notifica di conservazione legale. Inoltre, se gli avvisi di sollecito/escalation sono abilitati, anche questi flussi di lavoro verranno riavviati. 


#### <a name="update-legal-hold-notifications-and-settings"></a>Aggiornare le notifiche e le impostazioni per il blocco legale

Quando si aggiorna il contenuto o le impostazioni dell'avviso di emissione, rilascio, riStampa, proMemoria o esCalation, queste modifiche verranno applicate a tutte le comunicazioni future generate dal flusso di lavoro.

## <a name="related-information"></a>Informazioni correlate 

- [Creare un avviso per la conservazione legale](create-hold-notification.md)
    
- [Confermare la ricezione di una notifica di blocco](acknowledge-hold-notification.md)
    
- [Aggiungere responsabili a un caso](add-custodians-to-case.md)