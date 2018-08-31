---
title: Applicare o rimuovere un criterio di eliminazione del documento per un sito
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo. Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali. Per questo motivo, la tua organizzazione potrebbe aver creato un criterio di eliminazione del documento per il tuo sito; per esempio, potrebbe essere necessario eliminare i documenti dell'attività generale cinque anni dopo la loro creazione.
ms.openlocfilehash: abee0da7adfba6f653743d503f8b30770ee93c40
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531211"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Applicare o rimuovere un criterio di eliminazione del documento per un sito

Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo. Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali. Per questo motivo, la tua organizzazione potrebbe aver creato un criterio di eliminazione del documento per il tuo sito; per esempio, potrebbe essere necessario eliminare i documenti dell'attività generale cinque anni dopo la loro creazione.
  
A seconda dell'organizzazione, un criterio di eliminazione del documento può essere:
  
- **Obbligatorio** Un proprietario del sito non può disattivare un criterio obbligatorio, viene automaticamente applicato al sito. 
    
- **Predefinito** Un criterio predefinito è applicato al sito automaticamente, ma il proprietario del sito può: 
    
  - Selezionare un altro criterio, se disponibile.
    
  - Disattivare completamente il criterio, se non è rilevante ai fini del contenuto del sito.
    
- **Né obbligatorio né predefinito** In questo caso, nessun criterio è applicato al sito automaticamente e il proprietario del sito deve eseguire determinate azioni per applicarne uno. 
    
Un criterio di eliminazione del documento può contenere più di una regola. Per esempio, una regola potrebbe definire l'eliminazione dei documenti dopo un anno dalla loro creazione, mentre un'altra regola potrebbe definire l'eliminazione dei documenti dopo un anno dall'ultima modifica apportata loro. Se un criterio contiene più di una regola, puoi selezionare quella più appropriata per il tuo sito. La regola di eliminazione verrà applicata a tutte le librerie all'interno del sito. Solo un criterio e una regola alla volta possono essere attivi in un sito. Come un criterio, anche una regola può essere impostata come predefinita, in modo che sia applicata automaticamente quando viene applicato il criterio corrispondente.
  
Infine, i criteri di eliminazione del documento vengono ereditati. Quando selezioni un criterio o una regola per il tuo sito, tale scelta viene ereditata da tutti i siti secondari, anche se il proprietario di un sito secondario può interrompere l'ereditarietà selezionando un criterio o una regola diversi. Quando selezioni un criterio o una regola, tieni presente il contenuto di eventuali siti secondari all'interno del tuo sito.
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a>Visualizzare i criteri di eliminazione del documento disponibili in una raccolta siti

La tua organizzazione può assegnare criteri diversi a raccolte siti diverse. A livello della raccolta siti, il proprietario di una raccolta siti può visualizzare tutti i criteri di eliminazione del documento disponibili per tale raccolta siti. I criteri possono essere stati resi disponibili per il modello della raccolta siti (e di conseguenza per tutte le raccolte siti create da quel modello) oppure per quella specifica raccolta siti.
  
1. Nel sito principale della raccolta siti, nell'angolo superiore destro, scegliere **Impostazioni** [icona ingranaggio] \> **Impostazioni sito**.
    
2. Nella sezione **Amministrazione raccolta siti** \> **criteri di eliminazione dei documenti**.
    
    > [!NOTE]
    > Il collegamento di **Criteri di eliminazione dei documenti** non viene visualizzato a meno che non sono stati assegnati i criteri per la raccolta siti. Inoltre, il collegamento non viene visualizzata immediatamente dopo che i criteri assegnati al sito, può richiedere fino a 24 ore da quando i criteri vengono assegnati a quando viene visualizzato il collegamento di **Criteri di eliminazione dei documenti** . 
  
3. In questa pagina puoi trovare:
    
  - I criteri attualmente assegnati e le regole associate. Seleziona un criterio per visualizzare le regole nel riquadro destro.
    
  - Se presente, il criterio predefinito presenta l'opzione **Sì** nella colonna **predefinita**. 
    
  - Se è stato assegnato un criterio **obbligatorio**, al di sotto dell'elenco viene visualizzato un messaggio.
    
Questo elenco è solo in modalità visualizzazione e consente al proprietario della raccolta siti di vedere tutti i criteri e le regole disponibili. Per informazioni sull'applicazione di un criterio, consulta la sezione successiva.
  
![Visualizzare i criteri di eliminazione dei documenti assegnati a una raccolta siti](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Applicare o rimuovere un criterio di eliminazione del documento per un sito

È possibile che la tua organizzazione abbia creato dei criteri che, in qualità di proprietario di un sito o di una raccolta siti, puoi sia applicare al tuo sito sia disattivare completamente.
  
1. Nell'angolo superiore destro, scegliere **Impostazioni** [icona ingranaggio] \> **Impostazioni sito**.
    
2. Nella sezione **Amministrazione sito** \> **criteri di eliminazione dei documenti**.
    
    > [!NOTE]
    > Il collegamento di **Criteri di eliminazione dei documenti** non viene visualizzato a meno che non sono stati assegnati i criteri per la raccolta siti. Inoltre, il collegamento non viene visualizzata immediatamente dopo che i criteri assegnati al sito, può richiedere fino a 24 ore da quando i criteri vengono assegnati a quando viene visualizzato il collegamento di **Criteri di eliminazione dei documenti** . 
  
3. Eseguire una delle operazioni seguenti:
    
  - **Per applicare un criterio** Selezionare un criterio \> selezionare una regola in quel criterio \> **salvare**.
    
    Solo un criterio e una regola alla volta possono essere attivi in un sito. L'organizzazione può fornire più criteri e regole tra cui scegliere oppure metterne a disposizione solo uno.
    
    ![Selezionare l'opzione criteri](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - **Per disattivare un criterio** Scegliere **con consenso esplicito: Nota Elimina** \> **salvare**.
    
    In qualità di proprietario del sito, puoi disattivare un criterio di eliminazione del documento se decidi che quel criterio non è applicabile al contenuto del sito. Tuttavia, non puoi disattivare un criterio che è stato contrassegnato come **obbligatorio**.
    
    ![Opzione di consenso esplicito fuori](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a>I criteri di eliminazione del documento ignorano altri criteri

Un sito può utilizzare altri criteri per il mantenimento e l'eliminazione dei contenuti:
  
- Criteri tipo di contenuto per la raccolta siti.
    
- Criteri di gestione delle informazioni per un elenco o una libreria.
    
Se si applica un criterio di eliminazione del documento a un sito che utilizza già criteri tipo di contenuto o criteri di gestione delle informazioni per un elenco o raccolta, i criteri vengono ignorati durante il criterio di eliminazione del documento attivo. Se vengono ignorate le altri criteri, verrà visualizzato il messaggio "Criteri di eliminazione documento il contenuto di questo sito viene utilizzato".
  
Questo significa che dovresti pianificare un sito che utilizzi solo criteri destinati a contenuti strutturati (criteri di gestione delle informazioni e criteri tipo di contenuto) o contenuti non strutturati (criteri di eliminazione del documento) e non ad entrambi. Se disattivi il criterio di eliminazione del documento, l'errore segnalato dall'avviso non verrà visualizzato e continueranno a funzionare altri tipi di criteri.
  
I criteri di eliminazione del documento non hanno alcun effetto sui criteri sito.
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a>Determinare se i criteri tipo di contenuto vengono ignorati

Se lo stava utilizzando il sito criteri tipo di contenuto ed è ora visualizzato il messaggio, i criteri non sono più attivo. Per ripristinare i criteri tipo di contenuto, è possibile rimuovere il criterio di eliminazione del documento dal sito, come descritto in precedenza, se è disponibile un'opzione di esclusione. Se non è disponibile alcuna opzione in modo esplicito, il criterio di eliminazione del documento è obbligatorio e si desidera contattare il responsabile della conformità all'interno dell'organizzazione.
  
1. Nell'angolo superiore destro, scegliere **Impostazioni** [icona ingranaggio] \> **Impostazioni sito**.
    
2. Nella sezione **Amministrazione sito** \> **modelli di criteri per il tipo di contenuto**.
    
    ![Avviso nel sito che vengono utilizzati criteri di eliminazione dei documenti](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a>Determinare se i criteri di gestione delle informazioni vengono ignorati

Se il sito è stato mediante criteri di gestione delle informazioni e viene ora visualizzato questo messaggio, i criteri non sono più attivo. Per ripristinare i criteri di gestione delle informazioni, è possibile rimuovere il criterio di eliminazione del documento dal sito, come descritto in precedenza, se è disponibile un'opzione di esclusione. Se non è disponibile alcuna opzione in modo esplicito, il criterio di eliminazione del documento è obbligatorio e si desidera contattare il responsabile della conformità all'interno dell'organizzazione.
  
- Per un elenco o raccolta, nella barra multifunzione \> scheda **raccolta** \> **Impostazioni raccolta** \> in **autorizzazioni e gestione** \> **Impostazioni criteri di gestione delle informazioni**.
    
    ![Avviso nel sito che vengono utilizzati criteri di eliminazione dei documenti](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a>Vedere anche

[Panoramica dei criteri di eliminazione dei documenti](document-deletion-policies.md)
  
[Creare un criterio di eliminazione dei documenti](create-a-document-deletion-policy.md)

