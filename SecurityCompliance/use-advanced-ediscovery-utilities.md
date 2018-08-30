---
title: Usare le utilità di Office 365 Advanced eDiscovery
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Per conoscere le utilità di eDiscovery Office 365 avanzate, tra cui registro casi, cancellare i dati, gli errori del processo, modificare pertinenza e la trasparenza analisi.  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530283"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a>Usare le utilità di Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Utilità che verranno visualizzati e disponibili in eDiscovery avanzate dipendono dal ruoli utente e di contesto.
  
## <a name="case-log"></a>Registro casi

Il registro del caso contiene un elenco dettagliato delle attività di elaborazione dell'applicazione, che può essere utilizzato per la tracciabilità, risoluzione dei problemi e per la risoluzione di errori e avvisi. Nel registro può essere generato e memorizzato localmente nel computer host o server o inviato direttamente a un indirizzo di posta elettronica.
  
Il file di registro può inoltre essere scaricato per il computer client. L'opzione di download del client può essere attivata o disattivata in base al ruolo utente e di configurazione.
  
1. Nella barra dei menu, fare clic sull'icona **Cogwheel** . 
    
2. Nella **impostazioni e le utilità \> utilità** , selezionare **registro casi \> il programma di installazione**.
    
3. Selezionare il **livello di registrazione** nel modo seguente: 
    
  - **Standard**: include i dati dei registri di base. Questa opzione è in genere necessaria per il monitoraggio e deve essere utilizzata a meno che non consigliato in caso contrario.
    
  - **Minimo**: utilizzato per i casi di grandi dimensioni e restituisce solo i dati più recenti.
    
4. Fare clic su **Registro Case eseguito**. Il registro generato e percorso viene visualizzato. Le informazioni sull'avanzamento delle attività per l'attività corrente e il cognome è visualizzati nel riquadro di stato attività.
    
## <a name="clear-data"></a>Cancella dati

Se è necessario eliminare o reinizializzare dati sui casi, l'istanza del database deve inizializzato. L'utilità Cancella dati Elimina specificate tutte le voci dal database maiuscole, file di testo, cartella sociale e risultati accumulati. La funzione può essere eseguita solo da un amministratore.
  
> [!IMPORTANT]
> Questa azione non è reversibile eliminerà tutti pertinenza tagging e analisi eseguita da un esperto. Salvare una copia di backup dei dati, se necessario. Utilizzare questa opzione con prestare particolare attenzione. Eliminazione dei file di tag e classificati può influire sui risultati della pertinenza. 
  
1. Nella barra dei menu, fare clic sull'icona **Cogwheel** . 
    
2. Nella **impostazioni e le utilità \> utilità** , selezionare **cancellare i dati \> il programma di installazione**.
    
3. Selezionare un'opzione per le informazioni necessarie per inizializzare:
    
  - **Pertinenza**: consente di eliminare tutte le operazioni eseguite in pertinenza, tra cui definizione dei carichi e associazione dei file e carichi. Elimina tutti gli esempi e tagging.
    
  - **Quasi duplicati e thread di posta elettronica**: consente di eliminare tutte le informazioni di analisi dei quasi duplicati e thread di posta elettronica.
    
  - **Temi**: consente di eliminare i dati relativi ai temi.
    
  - **Esporta la cronologia**: consente di eliminare le informazioni della cronologia del batch di esportazione.
    
4. Fare clic su **Cancella dati**. I dati maiuscole sia deselezionati. Le informazioni sull'avanzamento delle attività per l'attività corrente e il cognome è visualizzati nel riquadro di **stato dell'attività** . 
    
## <a name="modify-relevance"></a>Modificare pertinenza

In questa sezione viene descritto come ignorare o eseguire il rollback di un campione di pertinenza.
  
1. Nella barra dei menu, fare clic sull'icona **Cogwheel** . 
    
2. Nella **impostazioni e le utilità \> utilità** selezionare **la pertinenza di modifica**.
    
3. Selezionare una delle opzioni: 
    
  - **Esempio corrente di elementi da ignorare - per l'utente corrente**: questo verrà contrassegnato, come **elementi da ignorare**tutti i file senza tag nell'esempio di maiuscole open dell'utente che esegue l'utilità. Elaborazione di pertinenza non verrà eseguito nel file contrassegnati come **Ignora**.
    
  - **Sample corrente di elementi da ignorare - all aprire esempi**: come **elementi da ignorare**questo verrà contrassegnare tutti i file senza tag negli esempi di tutte le finestra per tutti gli utenti. Questa opzione non è consigliata se gli utenti sono attualmente tagging esempi.
    
  - **Eseguire il rollback di esempio ultimo**: l'ultimo completato pertinenza campione per verrà annullata, indipendentemente dal fatto che sia prima o dopo il processo di "Calcolo". Rollback di un campione di aggiornamento non è consentito.
    
4. Fare clic su **Esegui** per eseguire. 
    
## <a name="transparency-analysis"></a>Analisi di trasparenza

L'utilità di analisi trasparenza consente una visualizzazione dettagliata dei file e loro assegnato punteggio di pertinenza. Il report può essere utilizzato come una verifica dell'integrità o per confrontare la pertinenza di un file definito da un revisore alla pertinenza assegnato da eDiscovery avanzate. 
  
Oltre a punteggio di pertinenza, eDiscovery avanzate calcola e assegna spessori parola chiave che considerare il contesto di parola chiave. La stessa parola in un file può essere assegnata diversi fattori, in base al contesto e il percorso. Ogni parola chiave è contrassegnato con una scala l'aumento di intensità del colore compreso giallo e arancione scuro e varying sfumature di grigio. La codifica dei colori viene utilizzata per indicare visivamente la parola parente contributo positivo o negativo per il punteggio di pertinenza. 
  
In uno scenario di maiuscole più problema, un report di analisi trasparenza può essere generato per ogni problema.
  
1. Nella barra dei menu, fare clic sull'icona **Cogwheel** . 
    
2. Nella **impostazioni e le utilità \> utilità** , selezionare **analysis trasparenza \> il programma di installazione**.
    
3. In * * File ID * *, immettere l'ID di file del file per l'elaborazione.
    
4. Nell'elenco **problema** , selezionare il problema pertinente. 
    
5. Fare clic su **analisi trasparenza**. Al termine, viene visualizzato il report di analisi di trasparenza del file di cui viene illustrato come i colori delle parole chiave contrassegnate essere correlato al punteggio di pertinenza globale.
    
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Definizione delle impostazioni di maiuscole e minuscole e tenant](define-case-and-tenant-settings-in-advanced-ediscovery.md)

