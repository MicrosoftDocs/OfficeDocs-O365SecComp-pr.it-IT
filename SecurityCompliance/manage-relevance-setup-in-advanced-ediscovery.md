---
title: Gestire la configurazione di Rilevanza in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: 'Elementi consigliati per configurare il training per la rilevanza in Office 365 Advanced eDiscovery per classificare i file in base alla rilevanza e generare risultati analitici.  '
ms.openlocfilehash: b2f1f848d14bdf77444c2026cbc675042c792542
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530391"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a>Gestire la configurazione di Rilevanza in Office 365 Advanced eDiscovery

> [!NOTE]
> Advanced eDiscovery richiede Office 365 E3 con il componente aggiuntivo Advanced Compliance o la sottoscrizione di E5 dell'organizzazione. Se non si dispone di questo piano e si desidera provare Advanced eDiscovery, è possibile [iscriversi a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 La tecnologia di rilevanza di Advanced eDiscovery applica software elaborato da specialisti per classificare i file in base alla rilevanza e può essere utilizzata per prime valutazioni dei casi (ECA, Early Case Assessment), eliminazione selettiva e revisione di campioni di file. 
  
 Advanced eDiscovery include componenti per il training di rilevanza e tag di file rilevanti per un caso, memorizza esempi di file rilevanti e non per classificare ogni file e generare risultati analitici che possono essere usati durante e dopo il processo di verifica dei file. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Linee guida per configurare il training di rilevanza

 In Advance eDiscovery, nella finestra di dialogo **Casi**, selezionare un caso e fare clic su **Passa al caso**. Fare clic su **Rilevanza** \> **Configurazione della rilevanza**. Seguire le linee guida consigliate per configurare la rilevanza. 
  
- **Aggiunta di tag**: l'efficacia del training di rilevanza dipende dall'abilità dello specialista di contrassegnare i campioni di file con precisione e coerenza.
    
- **Problemi di casi**: 
    
  - Per ogni problema, utilizzare lo stesso specialista per l'intero processo di training di rilevanza. Aggiungere contemporaneamente tag da più specialisti non è consentito.
    
  - Determinare se ogni gruppo di file è pertinente solo per un problema specifico. 
    
  - Se un problema è definito in modo troppo generico, Advanced eDiscovery potrebbe produrre troppi file che in realtà non sono rilevanti. Se un problema è definito in modo troppo ristretto, il processo di training di rilevanza potrebbe richiedere più tempo. 
    
  - Durante ciascun ciclo di training di rilevanza, Advanced eDiscovery si concentra su un singolo problema attivo e i risultati dei campioni intermedi vengono visualizzati di conseguenza.
    
  - In uno scenario con più problemi, la modalità campione consente di selezionare i problemi da includere nell'elaborazione. I problemi "inattivi" non vengono gestiti fino a quando la loro modalità di campionamento non viene modificata. Un problema può essere "inattivo" o "attivato" per un solo specialista.
    
  -  Advanced eDiscovery può essere usato per generare file di privilegi candidati. Configurare un problema separato in base al privilegio. Se possibile, prima eseguire il training ed eliminare in base alla rilevanza, quindi eseguire il training in base al privilegio solo sul set eliminato (ricaricare il set eliminato come caso separato). 
    
  - Il calcolo del batch può essere eseguito solo quando non sono presenti campioni aperti (quando si fa clic su Calcolo batch, verrà visualizzato un elenco di utenti con campioni aperti). Per "chiudere" i campioni di altri utenti (questo dovrebbe essere eseguito solo se questi utenti non contrassegnano questi esempi), un amministratore può utilizzare l'utilità "Modifica rilevanza" con l'opzione "Tutti i campioni di utenti".
    
- **Metadati**: Advanced eDiscovery si concentra sul contenuto. Non considera i metadati nell'ambito dei criteri di rilevanza. 
    
- **Rilevanza**: se la rilevanza di un problema ha un valore inferiore al 3% dopo la valutazione, si consiglia di effettuare il seeding del training di rilevanza con file rilevanti e non rilevanti.
    
- **Dimensione del file**: i file di grandi dimensioni (oltre 5.242.880 caratteri di testo estratto) vengono ignorati nella rilevanza. I file non partecipano al training di rilevanza e non vengono classificati per rilevanza dopo il calcolo del batch. I file oltre i 5 MB possono essere inclusi nel set di valutazione.
    
## <a name="setting-up-case-issues"></a>Configurazione di problemi dei casi

I parametri descritti in questa sezione sono disponibili nella tecnologia di rilevanza di Advanced eDiscovery **** \> **Configurazione della rilevanza**. 
  
- I problemi devono essere assegnati a un utente che dovrà occuparsi del training dei file.
    
- I file importati devono quindi essere aggiunti al carico di elaborazione.
    
- Definire e organizzare con attenzione i problemi, poiché i risultati del training di rilevanza possono esserne influenzati.
    
Dopo aver impostato i parametri, il revisore/lo specialista può avviare il training r dei file nella scheda **Rilevanza**. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Definire i problemi e assegnare gli utenti](define-issues-and-assign-users.md)
  
[Configurare carichi per aggiungere file importati](set-up-loads-to-add-imported-files.md)
  
[Definire parole chiave evidenziate e opzioni avanzate](define-highlighted-keywords-and-advanced-options.md)

