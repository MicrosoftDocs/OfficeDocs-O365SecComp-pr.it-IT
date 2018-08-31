---
title: Creare un criterio di eliminazione dei documenti
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: Alle organizzazioni viene spesso richiesto di conservare i documenti per un determinato periodo di tempo a causa di norme legate alla conformità, legali o di altro tipo. Tuttavia, conservare i documenti per un periodo superiore a quello richiesto può esporre l'organizzazione a un rischio legale.
ms.openlocfilehash: 115e4d7df93d81e7ee5a860f20a00d9cb175f927
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23014000"
---
# <a name="create-a-document-deletion-policy"></a>Creare un criterio di eliminazione dei documenti

> [!IMPORTANT]
> Spostarsi avanti, è consigliabile utilizzare un criterio di conservazione o etichette create per la protezione &amp; centro conformità anziché un criterio di eliminazione del documento. Criteri di eliminazione dei documenti continuerà a funzionare Affianca i criteri di conservazione, ma se è necessario mantenere o eliminare contenuto via Internet in Office 365, è consigliabile utilizzare un criterio di conservazione. Per ulteriori informazioni, vedere [utilizzare un criterio di conservazione invece di queste funzionalità](retention-policies.md#use-a-retention-policy-instead-of-these-features). 
  
Alle organizzazioni viene spesso richiesto di conservare i documenti per un determinato periodo di tempo a causa di norme legate alla conformità, legali o di altro tipo. Tuttavia, conservare i documenti per un periodo superiore a quello richiesto può esporre l'organizzazione a un rischio legale.
  
Con un criterio di eliminazione dei documenti, è possibile ridurre in modo proattivo rischio eliminando i documenti in un sito dopo un periodo di tempo specifico, ad esempio, è possibile eliminare documenti OneDrive degli utenti per Business siti cinque anni dopo che sono stati creati i documenti. 
  
Dopo aver creato un criterio di eliminazione dei documenti, puoi assegnarlo a un modello di raccolta siti, in modo che il criterio sia disponibile per tutte le raccolte di siti create da tale modello. Puoi anche assegnare il criterio a una raccolta di siti specifica, sostituendo tutti i criteri che potrebbero essere stati assegnati al modello di tale raccolta di siti.
  
![Home page del Centro criteri per l'eliminazione dei documenti](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a>Modelli dei criteri

È possibile creare dei criteri per l'eliminazione dei documenti da zero o utilizzare uno dei criteri di esempio. Il centro criteri di conformità include dei criteri di esempio che è possibile utilizzare così come sono. In alternativa, è possibile usarli come punto di partenza per poi rinominarli o modificarli.
  
![Criteri di eliminazione del documento di esempio](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a>Esempi di come utilizzare i criteri di eliminazione dei documenti

Una raccolta siti o un modello di raccolta siti può avere uno più criteri a esso assegnati e ognuno di questi criteri può avere una o più regole. Tuttavia, può esistere solo un criterio che è attivo per ogni sito e può esistere una sola regola di eliminazione è attiva in qualsiasi momento per le raccolte all'interno del sito.
  
![Diagramma con relazione tra criteri](media/IP-Two-policies-four-rules.png)
  
Inoltre, puoi selezionare un criterio come obbligatorio o predefinito e puoi selezionare una regola di eliminazione come regola predefinita: 
  
- **Criterio obbligatorio** Quando un criterio viene contrassegnato come obbligatorio, è possibile assegnare un solo criterio alla raccolta siti o del modello. Il criterio deve essere contrassegnato come predefinito e verrà applicato a tutti i siti. I proprietari del sito non possono disattivare completamente il criterio.
    
- **Criterio predefinito** Quando un criterio viene contrassegnato come predefinito, il criterio è automaticamente attivo in tutti i siti che è assegnato con proprietario del sito debba eseguire alcuna operazione.
    
- **Regola predefinita** Quando una regola di eliminazione viene configurata come predefinita, viene automaticamente applicata a tutte le librerie nei siti che usano il criterio.
    
Nei seguenti esempi viene spiegato quando occorre usare un criterio obbligatorio o criteri e regole predefinite.
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a>Esempio 1: applicare un solo criterio con una sola regola a un modello di raccolta di siti

Potresti voler applicare un criterio di eliminazione dei documenti in un'ampia gamma di contenuto non strutturato, come i siti di OneDrive for Business o del team. Se vuoi essere sicuro che un solo criterio di eliminazione dei documenti sia attivo in tutti i siti creati da un modello di raccolta siti, puoi:
  
1. Creare un unico criterio con una sola regola di eliminazione predefinita.
    
2. Impostare il criterio come obbligatorio e predefinito.
    
3. Assegnare il criterio a un modello di raccolta siti.
    
In questo esempio, la regola di eliminazione predefinita verrà applicata a tutti le librerie in tutte le raccolte di siti create dal modello, e i proprietari del sito non potranno rifiutare esplicitamente il criterio. Questo è il modo più semplice per applicare su vasta scala e rigidamente un criterio di eliminazione dei documenti.
  
![Diagramma con un solo criterio obbligatorio](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a>Nell'esempio 2: Applicare un solo criterio con diverse regole a un modello di raccolta siti

I proprietari del sito spesso conoscono bene il tipo di contenuto presente nel sito, quindi potresti scegliere di consentire ai proprietari del sito di selezionare la regola di eliminazione più adatta al loro sito. Potresti inoltre voler consentire ai proprietari del sito di rifiutare completamente un criterio.
  
Allo stesso tempo, puoi comunque creare e gestire centralmente i criteri. Puoi anche selezionare un criterio e una regola come predefiniti, in modo che un criterio sia sempre valido finché il proprietario non ne sceglie uno diverso o lo rifiuti. Se vuoi offrire tale flessibilità ai proprietari del sito, puoi:
  
1. Creare un solo criterio con diverse regole di eliminazione e impostare una regola come predefinita.
    
2. Impostare il criterio come criterio predefinito.
    
3. Assegnare il criterio a un modello di raccolta siti.
    
I proprietari del sito possono selezionare una delle regole di eliminazione alternative, rifiutare il criterio o non fare nulla ed essere soggetti al criterio e alla regola predefiniti.
  
![Diagramma con un criterio con molte regole](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a>Esempio 3: applicare diversi criteri con una o più regole a una raccolta siti

Questo esempio offre la massima flessibilità ai proprietari del sito perché possono scegliere tra diversi criteri e dopo aver selezionato un criterio, possono spesso scegliere tra diverse regole. Un criterio e una regola vengono impostati come predefiniti, in modo che un criterio sia sempre valido finché il proprietario del sito non ne sceglie uno diverso o lo rifiuti. Tieni presente che se non imposti un criterio e una regola come predefiniti, nessun criterio o nessuna regola saranno attivi per le librerie di documenti nel sito finché il proprietario del sito non li selezionerà e applicherà.
  
Diversamente dai due esempi precedenti, questi criteri vengono assegnati a una raccolta di siti specifica, non al modello di raccolta di siti. Ciò significa che i criteri possono essere ancora più specificatamente personalizzati in base al contenuto in una raccolta di siti specifica.
  
I criteri e le regole sono ereditate. I proprietari del sito possono selezionare una regola e un criterio per il proprio sito e tutti i siti secondari erediteranno il criterio dal sito principale. Tuttavia, un proprietario di un sito secondario può interrompere l'ereditarietà selezionando un altro criterio e un'altra regola, che a loro volta verranno applicati a tutti i siti secondari finché l'ereditarietà non verrà di nuovo interrotta.
  
Per impostare questo scenario, puoi:
  
1. Creare diversi criteri che contengono una o più regole.
    
2. Impostare un criterio e una regola come predefiniti.
    
3. Assegnare i criteri a una raccolta siti specifica.
    
Inoltre, i criteri e le regole vengono creati in base a una raccolta di siti specifica, dove i proprietari del sito possono interrompere l'ereditarietà selezionando il criterio e la regola più adatti al proprio sito.
  
![Diagramma con molti criteri e regole](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a>Creare un criterio di eliminazione dei documenti

1. In 365Security Office &amp; centro conformità, passare a **gestione dei dati** \> **conservazione**. In **Elimina**, fare clic su **Gestisci criteri di eliminazione dei documenti di SharePoint Online e OneDrive for Business**. Il centro di criteri di eliminazione documento verrà aperto in una nuova scheda browser.
    
    La prima volta passare dal titolo &amp; centro conformità all'interfaccia di criteri di eliminazione di documenti, il centro dei criteri viene automaticamente creato. In alternativa, è possibile creare manualmente il centro di criterio [della raccolta siti di creazione](http://go.microsoft.com/fwlink/p/?LinkID=404342) e scegliendo **Centro conformità criteri** nella scheda **organizzazione** . 
    
2. Scegliere **i criteri di eliminazione**.
    
    ![Opzione Elimina criteri](media/IP-Deletion-Policies-option.png)
  
3. Scegli **nuovo elemento**.
    
4. Inserisci un nome e una descrizione per il criterio. I proprietari del sito possono selezionare un criterio per il proprio sito in base al nome o alla descrizione, quindi ti consigliamo di inserire abbastanza informazioni per permettergli di scegliere il criterio corretto.
    
5. Per creare una regola, scegli **Nuova**.
    
6. Inserisci un nome e scegli le seguenti opzioni:
    
  - Scegliere se la regola sarà eliminazione documenti o eliminarli nel Cestino. Cestino fornisce una rete sicura Cestino prima che un elemento viene eliminato definitivamente da un sito. Per ulteriori informazioni su Cestino, vedere [svuotare il Cestino o il ripristino dei file](http://go.microsoft.com/fwlink/p/?LinkID=404348).
    
  - Scegli se la data di eliminazione deve essere creata dalla data di creazione del documento a da quella dell'ultima modifica.
    
  - Inserisci un numero di giorni, mesi o anni come periodo di tempo dopo il quale un documento deve essere eliminato.
    
  - Scegli se la regola è una regola predefinita. La prima regola creata viene automaticamente impostata come la regola predefinita. Una regola predefinita viene automaticamente applicata a tutte le librerie nei siti che usano il criterio.
    
![Pagina Nuova regola di eliminazione](media/IP-New-deletion-rule.png)
  
7. Fare clic su **Salva**.
    
8. Crea regole aggiuntive se vuoi che i proprietari del sito possano scegliere diverse regole da applicare al proprio sito. Verrà applicata la regola predefinita, se presente, se il proprietario del sito non esegue alcuna azione.
    
9. Per rimuovere una regola da un criterio, selezionare la regola, fare clic su **Elimina**e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se si elimina una regola, il criterio non contiene una regola predefinita, quindi alcuna regola non verrà attivata per tale criterio, in altre parole, non i documenti verranno eliminati. 
  
![Messaggio di conferma dell'eliminazione di una regola da un criterio](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a>Assegnare il criterio di eliminazione dei documenti a un modello di raccolta di siti

Assegnando un criterio a un modello di raccolta di siti, puoi rendere disponibile il criterio per tutte le raccolte di siti create dal tale modello, comprese le raccolte di siti esistenti e le raccolte di siti create nel futuro.
  
È importante tenere presente che il periodo di tempo specificato per un documento di un criterio di eliminazione indica il tempo in quanto il documento è stato creato o modificato, non l'ora in quanto è stato assegnato il criterio. Quando si assegna il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano i criteri, verranno eliminati. Ciò vale per tutti i documenti, non appena nuovi documenti creati in quanto è stato assegnato il criterio.
  
1. In sicurezza &amp; centro conformità, passare a **gestione dei dati** \> **conservazione**. In **Elimina**, fare clic su **Gestisci criteri di eliminazione dei documenti di SharePoint Online e OneDrive for Business**. Il centro di criteri di eliminazione documento verrà aperto in una nuova scheda browser.
    
2. Scegli **Assegnazioni dei criteri per i modelli**.
    
    ![Opzione Assegnazioni criteri per modelli](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. Scegli **nuovo elemento**.
    
4. Eseguire una delle operazioni seguenti:
    
  - Per assegnare il criterio a un modello di raccolta di siti come il modello Siti del team, seleziona **Assegna a un modello di raccolta di siti**, quindi seleziona il modello di raccolta di siti.
    
  - Per assegnare il criterio a One Drive degli utenti per le aziende, scegliere **assegnare a OneDrive for Business modello**, evidenziato in basso.
    
    > [!NOTE]
    > Quando assegni un criterio a un modello di raccolta di siti, tale criterio sarà disponibile sia per le raccolte di siti esistenti create dal modello, sia per quelle che verranno create in futuro. 
  
![Pagina di scelta di un modello con opzione OneDrive](media/IP-Choose-a-template.png)
  
5. Fare clic su **Salva**.
    
    > [!NOTE]
    > Ogni modello può avere un solo set di criteri a esso assegnato. Se viene visualizzato un errore indicante che questo modello include già i criteri assegnati a esso, scegliere **Annulla** \> **assegnare alla raccolta siti** nel riquadro di spostamento sinistro \> selezionare una raccolta siti per visualizzare e gestire set di criteri che sono già assegnato. 
  
6. Scegli **Gestisci criteri assegnati**, selezionare i criteri che si desidera assegnare e quindi scegliere se un criterio è il criterio predefinito. Quando si imposta un criterio predefinito, tutti i siti assegnati al criterio automaticamente hanno il criterio attivo con proprietario del sito debba eseguire alcuna operazione.
    
    ![Pagina di aggiunta e gestione criteri](media/IP-Add-and-manage-policies-page.png)
  
7. Fare clic su **Salva**.
    
8. Se vuoi applicare il criterio nei siti senza consentire ai proprietari del sito di rifiutarlo, scegli **Contrassegna il criterio come obbligatorio**. Quando rendi un criterio obbligatorio, solo il singolo criterio può essere assegnato al modello di raccolta di siti. Il criterio deve essere contrassegnato anche come predefinito.
    
    Se questa opzione è in grigio, scegli **Gestisci criteri assegnati** e controlla che almeno un criterio sia assegnato e impostato come predefinito. 
    
9. Fare clic su **Salva**.
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a>Assegnare il criterio di eliminazione dei documenti a una raccolta di siti

Assegnando un criterio a una raccolta di siti specifica, rendi disponibile il criterio solo per tale raccolta di siti specifica. Ciò significa che puoi meglio adattare i criteri al contenuto della raccolta di siti. Inoltre, i criteri assegnati a una raccolta di siti specifica sostituiranno tutti i criteri assegnati al modello di tale raccolta di siti. Ad esempio, un criterio assegnato alla raccolta di siti Reparto vendite (creato dal modello Siti del team) sostituirà tutti i criteri assegnati al modello Siti del team.
  
È importante tenere presente che il periodo di tempo specificato per un documento di un criterio di eliminazione indica il tempo in quanto il documento è stato creato o modificato, non l'ora in quanto è stato assegnato il criterio. Quando si assegna il criterio per la prima volta, tutti i documenti nel sito vengono valutati e, se soddisfano i criteri, verranno eliminati. Ciò vale per tutti i documenti, non appena nuovi documenti creati in quanto è stato assegnato il criterio.
  
1. In sicurezza &amp; centro conformità, passare a **gestione dei dati** \> **conservazione**. In **Elimina**, selezionare **Gestisci criteri di eliminazione dei documenti di SharePoint Online e OneDrive for Business**. Il centro di criteri di eliminazione documento verrà aperto in una nuova scheda browser.
    
2. Scegli **Assegnazioni dei criteri per le raccolte di siti**.
    
    ![Opzione Assegnazioni criteri per raccolte di siti](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. Scegli **nuovo elemento**.
    
4. Scegli **Scegli una raccolta siti**. Ricerca per la raccolta siti per nome o URL, selezionare la raccolta siti e fare clic su **Salva**.
    
    > [!NOTE]
    > Ogni raccolta siti può includere solo un set di criteri a esso assegnato. Se viene visualizzato un errore indicante che sito contiene già i criteri assegnati a esso, scegliere **Annulla** \> **assegnare alla raccolta siti** e selezionare una raccolta siti per visualizzare e gestire set di criteri che sono già state assegnate. 
  
![Pagina di scelta raccolta di siti](media/IP-Choose-a-site-collection-page.png)
  
5. Scegli **Gestisci criteri assegnati**, selezionare i criteri che si desidera assegnare e quindi scegliere se un criterio è il criterio predefinito. Quando si imposta un criterio predefinito, tutti i siti assegnati al criterio automaticamente hanno il criterio attivo con proprietario del sito debba eseguire alcuna operazione.
    
    ![Pagina di aggiunta e gestione criteri](media/IP-Add-and-manage-policies-page.png)
  
6. Fare clic su **Salva**.
    
7. Se vuoi applicare il criterio nei siti senza consentire ai proprietari del sito di rifiutarlo, scegli **Contrassegna il criterio come obbligatorio**. Quando rendi un criterio obbligatorio, solo il singolo criterio può essere assegnato alla raccolta di siti. Il criterio deve essere contrassegnato anche come predefinito.
    
    Se questa opzione è in grigio, scegli **Gestisci criteri assegnati** e controlla che almeno un criterio sia assegnato e impostato come predefinito. 
    
8. Fare clic su **Salva**.
    
## <a name="delete-a-policy-assignment"></a>Eliminare l'assegnazione di un criterio

Quando elimini un'assegnazione, i criteri assegnati non verranno più applicati ai siti nella raccolta di siti o nel modello di raccolta di siti.
  
1. In sicurezza &amp; centro conformità, passare a **gestione dei dati** \> **conservazione**. In **Elimina**, selezionare **Gestisci criteri di eliminazione dei documenti di SharePoint Online e OneDrive for Business**. Il centro di criteri di eliminazione documento verrà aperto in una nuova scheda browser.
    
2. Scegliere una delle opzioni **Assegnazioni dei criteri per i modelli** o **Assegnazioni dei criteri per le raccolte di siti**.
    
3. Selezionare l'elemento di assegnazione e fare clic su **Elimina elemento**.
    
    ![Comando Elimina elemento per assegnazione criterio](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a>Eliminare un criterio

È possibile eliminare un criterio in uso. Prima che è possibile eliminare un criterio, è innanzitutto necessario eliminare tutte le assegnazioni per le raccolte siti e modelli di raccolte siti che includono il criterio, vedere la sezione precedente.
  
1. In sicurezza &amp; centro conformità \> scegliere **gestione dati** \> **conservazione** nel riquadro di spostamento sinistro \> in **Elimina** \> **eliminazione documenti Gestisci criteri per SharePoint Online e OneDrive per le aziende**. Il centro di criteri di eliminazione documento verrà aperto in una nuova scheda browser.
    
2. Scegliere * * i criteri di eliminazione * *.
    
    ![Opzione Elimina criteri](media/IP-Deletion-Policies-option.png)
  
3. Seleziona il criterio.
    
4. Sulla barra multifunzione \> scheda **elementi** \> **Rimuovi elemento**.
    
    ![Pulsante Rimuovi criterio sulla barra multifunzione](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. Se il criterio è in uso, verrà richiesto se si desidera rimuovere il criterio da tutte le raccolte siti in cui viene utilizzato. Se si è certi, fare clic su **OK**.
    
    ![Messaggio di conferma eliminazione criterio](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a>Vedere anche

[Panoramica dei criteri di eliminazione dei documenti](document-deletion-policies.md)

[Applicare o rimuovere un criterio di eliminazione del documento per un sito](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

