---
title: Configurare un criterio di archiviazione e l'eliminazione delle cassette postali nell'organizzazione Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: Creare un criterio di archiviazione e l'eliminazione in Office 365 che sposta automaticamente gli elementi della cassetta postale di archivio dell'utente.
ms.openlocfilehash: 740164ee840a32aff20f5c2dc1b1ae433d95cfe5
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522297"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a>Configurare un criterio di archiviazione e l'eliminazione delle cassette postali nell'organizzazione Office 365

 **In questo articolo sia per gli amministratori. Aggiungere criteri di conservazione e archiviazione di elementi della cassetta postale? Vedere [assegnare i criteri di conservazione per i messaggi di posta elettronica](https://support.office.com/article/3e5fd2dc-633f-4a38-b313-b31b81f7cf7a) | [criteri di conservazione e archiviazione in Outlook sul web per le aziende](https://support.office.com/article/465372e4-e16b-47db-bee0-aba44799085e)**
  
In Office 365, è possibile creare un criterio di archiviazione e l'eliminazione automaticamente Sposta gli elementi della cassetta postale di archivio dell'utente, che elimina automaticamente gli elementi dalla cassetta postale. Tale scopo, è possibile creare un criterio di conservazione ' s assegnati alle cassette postali e gli elementi di spostamenti cassetta postale dell'utente di archiviazione dopo un determinato periodo di tempo e che anche Elimina gli elementi dalla cassetta postale dopo un determinato periodo di validità. Le regole effettive determinano quali elementi sono spostati o eliminati e in questo caso i tag di conservazione chiamato. I tag di conservazione collegati a un criterio di conservazione, a sua volta assegnato alla cassetta postale dell'utente. Un tag di conservazione applicato le impostazioni di conservazione a singoli messaggi e cartelle nella cassetta postale dell'utente. Consente di definire quanto tempo un messaggio rimane nella cassetta postale e l'azione che viene eseguita quando il messaggio raggiunge il periodo di conservazione specificato. Quando un messaggio raggiunge il periodo di conservazione, viene spostato alla cassetta postale di archivio dell'utente o che venga eliminato. 
  
I passaggi descritti in questo argomento verranno impostare un criterio di conservazione e archiviazione per un'organizzazione fittizia denominata neve accesso a terze parti. Impostazione di questo criterio include le attività seguenti:
  
- Abilitazione di una cassetta postale di archiviazione per tutti gli utenti nell'organizzazione. Consente agli utenti di archiviazione delle cassette postali di aggiunta ed è necessario in modo che un criterio di conservazione può spostare gli elementi di cassetta postale di archivio. È inoltre possibile un informazioni archiviazione dell'archivio utente per lo spostamento degli elementi loro cassetta postale di archiviazione. 
    
- Creazione di tre tag di conservazione personalizzata che eseguire le operazioni seguenti: 
    
  - Si sposta automaticamente gli elementi 3 anni precedenti alla cassetta postale di archivio dell'utente. Spostamento di elementi per la cassetta postale di archiviazione consente di liberare spazio nella cassetta postale principale dell'utente.
    
  - Elimina automaticamente gli elementi 5 anni dalla cartella Posta eliminata. Questo inoltre consente di liberare spazio nella cassetta postale principale dell'utente. Dell'utente avrà la possibilità di ripristinare questi elementi, se necessario. Il piè di pagina nella sezione [informazioni](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) per ulteriori informazioni, vedere. 
    
  - (E automaticamente in modo permanente) consente di eliminare gli elementi 7 anni da entrambi il primario e cassetta postale di archivio. A causa di regole di conformità, per mantenere posta elettronica per un determinato periodo di tempo è necessari alcuni dell'organizzazione. Dopo la scadenza del periodo, un'organizzazione possibile rimuovere definitivamente questi elementi cassette postali degli utenti. 
    
- Crea un nuovo criterio di conservazione, aggiungere i nuovi tag di conservazione personalizzata. Inoltre, si verranno inoltre aggiungere i tag di conservazione incorporato il nuovo criterio di conservazione. Sono inclusi i tag personali che gli utenti possono assegnare agli elementi nella cassetta postale. Sarà inoltre aggiungere un tag di conservazione che sposta gli elementi dalla cartella elementi ripristinabili nella cassetta postale principale dell'utente per la cartella elementi ripristinabili nella cassetta postale di archivio. Questo consente di liberano spazio nella cartella elementi ripristinabili dell'utente durante la propria cassetta postale viene messa in attesa.
    
È possibile eseguire alcuni o tutti i passaggi descritti in questo articolo per configurare un criterio di archiviazione e l'eliminazione delle cassette postali nell'organizzazione. È consigliabile testare il processo in alcune cassette postali prima di implementare in tutte le cassette postali nell'organizzazione.
  
## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere un amministratore globale dell'organizzazione Office 365 per eseguire i passaggi descritti in questo argomento. 
    
-  Quando si crea un nuovo account utente in Office 365 e si assegna all'utente una licenza di Exchange Online, viene automaticamente creata una cassetta postale dell'utente. Quando viene creata la cassetta postale, è stato assegnato automaticamente da un criterio di conservazione predefinito denominato criterio di gestione record di messaggistica predefinito. In questo articolo verranno creare un nuovo criterio di conservazione e quindi assegnarlo a cassette postali degli utenti, sostituendo il criterio di gestione record di messaggistica predefinito. Una cassetta postale può avere un solo criterio di conservazione a esso assegnato in qualsiasi momento.
    
- Per ulteriori informazioni sui tag di conservazione e criteri di conservazione in Exchange Online, vedere [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a>Passaggio 1: Cassette postali Abilita archiviazione per gli utenti

Il primo passaggio consiste per abilitare la cassetta postale di archiviazione per ogni utente nell'organizzazione. Cassetta postale di archivio dell'utente deve essere attivata in modo che un tag di conservazione con un'azione di conservazione "Movetoarchive" possibile spostare l'elemento dopo la scadenza del periodo di conservazione. 
  
> [!NOTE]
> È possibile abilitare cassette postali di archiviazione qualsiasi momento durante questo processo, esattamente come sono abilitati a un certo punto prima di completare il processo. Se una cassetta postale di archiviazione non è abilitata, viene eseguita alcuna azione in tutti gli elementi con un criterio di archiviazione a esso assegnato. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account amministratore globale.
    
    
3. In sicurezza &amp; centro conformità, Vai alla **governance dati** \> **Archive**.
    
    Viene visualizzato un elenco delle cassette postali nell'organizzazione e indica se la corrispondente cassetta postale di archiviazione è abilitata o disabilitata. 
    
4. Selezionare tutte le cassette postali facendo clic sul primo nell'elenco, tenere premuto il tasto **MAIUSC** e quindi fare clic su quello precedente nell'elenco. 
    
    > [!TIP]
    > Questo passaggio si presuppone che non contiene cassette postali di archiviazione sono attivati. Se si dispongono di tutte le cassette postali con l'archivio abilitato, tenere premuto il tasto **Ctrl** e fare clic su ciascuna cassetta postale che dispone di una cassetta postale di archivio disabilitati. Oppure è possibile fare clic sull'intestazione di colonna **cassetta postale di archiviazione** per ordinare le righe in base al fatto cassetta postale di archiviazione è abilitata o disabilitata per rendere più semplice selezionare le cassette postali. 
  
5. Nel riquadro dei dettagli, sotto **Modifica in blocco**, fare clic su **Abilita**.
    
    Viene visualizzato un avviso indicante che la nuova cassetta postale di archiviazione verranno spostati gli elementi che hanno superati due anni. Ciò avviene perché il criterio di conservazione predefinito che è assegnato a una nuova cassetta postale utente quando viene creata con un tag dei criteri di archiviazione predefinito che dispone di un periodo di conservazione di 2 anni. Il tag dei criteri predefiniti archivio personalizzato che verrà creata nel passaggio 2 è un periodo di conservazione di 3 anni. Ciò significa che gli elementi 3 anni o meno recenti verrà spostato la cassetta postale di archiviazione.
    
6. Fare clic su **Sì** per chiudere il messaggio di avviso e avviare il processo per abilitare la cassetta postale di archivio per ciascuna cassetta postale selezionata. 
    
7. Una volta completato il processo, fare clic su **Aggiorna** ![aggiornamento](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) per aggiornare l'elenco nella pagina **archivio** . 
    
    Cassetta postale di archiviazione è abilitata per tutti gli utenti nell'organizzazione.
    
    ![L'elenco delle cassette postali con la cassetta postale di archivio abilitato](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. Lasciare la sicurezza &amp; Apri Centro conformità. Verrà utilizzato nel passaggio successivo.
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Passaggio 2: Creare nuovi tag di conservazione per i criteri di archiviazione ed eliminazione

In questo passaggio verrà creato il tag di conservazione personalizzata tre descritte in precedenza.
  
- Neve civico 3 anno Sposta nell'archivio (criteri di archiviazione personalizzate)
    
- Neve House 7 anno eliminare definitivamente (criteri di eliminazione personalizzati)
    
- Neve anni 5 di elementi eliminati House Elimina e Consenti ripristino (tag personalizzati per la cartella Posta eliminata)
    
Per creare nuovi tag di conservazione, si utilizzerà l'interfaccia di amministrazione di Exchange (EAC) nell'organizzazione Exchange Online.
  
1. In sicurezza &amp; centro conformità, fare clic su avvio app nell'angolo superiore sinistro e quindi fare clic su tessera di **amministrazione** . 
    
2. Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Office 365, fare clic su **Admin Center**e quindi fare clic su **Exchange**.
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. In EAC, andare a **Gestione conformità** \> **i tag di conservazione**
    
    Viene visualizzato un elenco dei tag di conservazione per la propria organizzazione.
    
### <a name="create-a-custom-archive-default-policy-tag"></a>Creare un tag dei criteri di archiviazione personalizzate predefinito
  
Per prima cosa, si creerà un tag dei criteri predefinito (DPT) di archivio personalizzato che sposta gli elementi la cassetta postale di archiviazione dopo 3 anni. 
  
1. Nella pagina **tag di conservazione** , fare clic su **nuovo tag**![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), quindi selezionare **applicato automaticamente alla cassetta postale intera (impostazione predefinita)**. 
    
2. Nella pagina **nuovo tag applicati automaticamente alla cassetta postale intera (impostazione predefinita)** , completare i seguenti campi: 
    
    ![Impostazioni per creare un nuovo tag criterio predefinito di archiviazione](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. **Nome** Digitare un nome per il nuovo tag di conservazione. 
    
2. **Azione di conservazione** Selezionare **Sposta nell'archivio** per spostare gli elementi la cassetta postale di archiviazione quando scade il periodo di conservazione. 
    
3. **Periodo di conservazione** Selezionare **quando l'elemento raggiunge l'età seguente (in giorni)** e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno spostati la cassetta postale di archiviazione dopo giorni 1095 (3 anni).
    
4. **Commento** (Facoltativo) Digitare un commento che illustra lo scopo del tag di conservazione personalizzata. 
    
3. Fare clic su **Salva** per creare l'archivio personalizzato DPT. 
    
    Il nuovo DPT archive viene visualizzato nell'elenco dei tag di conservazione.
    
### <a name="create-a-custom-deletion-default-policy-tag"></a>Creare un tag dei criteri di eliminazione personalizzato predefinito
  
Successivamente, verrà creata un'altra DPT personalizzato ma questo è un criterio di eliminazione che consente di eliminare definitivamente gli elementi dopo 7 anni.
  
1. Nella pagina **tag di conservazione** , fare clic su **nuovo tag**![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), quindi selezionare **applicato automaticamente alla cassetta postale intera (impostazione predefinita)**. 
    
2. Nella pagina **nuovo tag applicati automaticamente alla cassetta postale intera (impostazione predefinita)** , completare i seguenti campi: 
    
    ![Impostazioni per creare un nuovo tag criterio predefinito di eliminazione](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. **Nome** Digitare un nome per il nuovo tag di conservazione. 
    
2. **Azione di conservazione** Selezionare **In modo permanente Elimina** per eliminare gli elementi dalla cassetta postale quando scade il periodo di conservazione. 
    
3. **Periodo di conservazione** Selezionare **quando l'elemento raggiunge l'età seguente (in giorni)** e quindi immettere la durata del periodo di conservazione. Per questo scenario in cui gli elementi verranno eliminati dopo 2555 giorni (7 anni).
    
4. **Commento** (Facoltativo) Digitare un commento che illustra lo scopo del tag di conservazione personalizzata. 
    
3. Fare clic su **Salva** per creare l'eliminazione personalizzato DPT. 
    
    Il nuovo DPT di eliminazione viene visualizzato nell'elenco dei tag di conservazione.
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Creare un tag dei criteri di conservazione personalizzata per la cartella Posta eliminata
  
L'ultimo tag di conservazione che verrà creata è un tag dei criteri di conservazione personalizzata (tag) per la cartella Posta eliminata. Questo tag eliminerà elementi nella cartella Posta eliminata dopo 5 anni e fornisce un punto di ripristino quando gli utenti possono utilizzare lo strumento Recupera elementi eliminati per recuperare un elemento.
  
1. Nella pagina **tag di conservazione** , fare clic su **nuovo tag** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), quindi selezionare **applicato automaticamente a una cartella predefinita**. 
    
2. Nella pagina **nuovo tag applicati automaticamente a una cartella predefinita** , completare i seguenti campi: 
    
    ![Impostazioni per creare un nuovo tag criterio di conservazione per la cartella Posta eliminata](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. **Nome** Digitare un nome per il nuovo tag di conservazione. 
    
2. **Applica questo tag nella cartella predefinita seguente** Nell'elenco a discesa selezionare **Posta eliminata**.
    
3. **Azione di conservazione** Selezionare **Elimina e Consenti ripristino** di eliminazione degli elementi quando scade il periodo di conservazione, ma consente di recuperare un elemento eliminato compresa nel periodo di mantenimento elementi eliminati (che per impostazione predefinita è 14 giorni). 
    
4. **Periodo di conservazione** Selezionare **quando l'elemento raggiunge l'età seguente (in giorni)** e quindi immettere la durata del periodo di conservazione. Per questo scenario, gli elementi verranno eliminati dopo giorni 1825 (5 anni).
    
5. **Commento** (Facoltativo) Digitare un commento che illustra lo scopo del tag di conservazione personalizzata. 
    
3. Fare clic su **Salva** per creare i tag personalizzati per la cartella Posta eliminata. 
    
    Il nuovo tag viene visualizzato nell'elenco dei tag di conservazione.

## <a name="step-3-create-a-new-retention-policy"></a>Passaggio 3: Creare un nuovo criterio di conservazione

Dopo aver creato i tag di conservazione personalizzata, il passaggio successivo consiste nel creare un nuovo criterio di conservazione e aggiungere i tag di conservazione. Si aggiungerà i tre tag di conservazione personalizzata creata nel passaggio 2 e i tag predefiniti descritti in precedenza nella prima sezione. Nel passaggio 4 si verrà assegnare questo nuovo criterio di conservazione alle cassette postali utente.
  
1. In EAC, andare a **Gestione conformità** \> **i criteri di conservazione**.
    
2. Nella pagina **criteri di conservazione** , fare clic su **Nuovo** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).
    
3. Nella casella **nome** digitare un nome per il nuovo criterio di conservazione; ad esempio **neve archivio di accesso a terze parti e criterio di eliminazione**. 
    
4. **I tag di conservazione**, fare clic su **Aggiungi** ![icona](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).
    
    Viene visualizzato un elenco dei tag di conservazione nella propria organizzazione. Si noti che vengono visualizzati i tag personalizzati creati nel passaggio 2.
    
5. Aggiungere i tag di conservazione 9 che vengono evidenziati nella schermata seguente (i tag vengono descritti dettagliatamente nella sezione [informazioni](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) ). Per aggiungere un tag di conservazione, selezionarlo e quindi fare clic su **Aggiungi**. 
    
    ![Aggiungere i tag di conservazione per il nuovo criterio di conservazione](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > È possibile selezionare più tag di conservazione tenendo premuto il tasto **Ctrl** e quindi facendo clic su ogni tag. 
  
6. Dopo aver aggiunto i tag di conservazione, fare clic su **OK**.
    
7. Nella pagina **nuovo criterio di conservazione** , fare clic su **Salva** per creare il nuovo criterio. 
    
    Il nuovo criterio di conservazione viene visualizzato nell'elenco. Selezionare se si desidera visualizzare i tag di conservazione collegati nel riquadro dei dettagli.
    
    ![Il nuovo criterio di conservazione e l'elenco dei tag di conservazione collegata](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Passaggio 4: Assegnare il nuovo criterio di conservazione alle cassette postali utente

Quando si crea una nuova cassetta postale, un criterio di conservazione denominato criterio di gestione record di messaggistica predefinito è assegnato a tale impostazione predefinita. In questo passaggio verrà sostituito il criterio di conservazione (perché una cassetta postale può avere un solo criterio di conservazione a esso assegnato) assegnando il nuovo criterio di conservazione creata nel passaggio 3 per le cassette postali degli utenti nell'organizzazione. Questo passaggio presuppone che verrà assegnato il nuovo criterio per tutte le cassette postali nell'organizzazione.
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Destinatari** \> **Cassette postali**.
    
    Viene visualizzato un elenco di tutte le cassette postali nell'organizzazione. 
    
2. Selezionare tutte le cassette postali facendo clic sul primo nell'elenco, tenere premuto il tasto **MAIUSC** e quindi fare clic su quello precedente nell'elenco. 
    
3. Nel riquadro dei dettagli a destra di Exchange, sotto **Modifica in blocco**, fare clic su **altre opzioni**.
    
4. In **Criterio di conservazione**, fare clic su **Aggiorna**.
    
5. Nella pagina **massa assegnare criteri di conservazione** nell'elenco a discesa **Selezionare il criterio di conservazione** , selezionare il criterio di conservazione creato nel passaggio 3; ad esempio, **i criteri di conservazione e archiviazione di casa neve**.
    
6. Fare clic su **Salva** per salvare la nuova assegnazione di criteri di conservazione. 
    
7. Per verificare che sia stato assegnato il nuovo criterio di conservazione alle cassette postali, è possibile eseguire le operazioni seguenti: selezionare una cassetta postale nella pagina cassette postali e quindi fare clic su Modifica. 
    
1. Selezionare una cassetta postale nella pagina **cassette postali** e quindi fare clic su **Modifica** ![modifica](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png). 
    
2. Nella pagina proprietà delle cassette postali per l'utente selezionato, fare clic su **funzionalità delle cassette postali**.
    
    Il nome del nuovo criterio assegnato alla cassetta postale viene visualizzato nell'elenco a discesa **criterio di conservazione** . 
    

  
## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Facoltativo) Passaggio 5: Eseguire l'Assistente cartelle gestite per applicare le nuove impostazioni
<a name="step3"> </a>

Dopo aver applicato il nuovo criterio di conservazione alle cassette postali nel passaggio 4, potrebbero essere necessari fino a 7 giorni di Exchange Online per le nuove impostazioni di conservazione da applicare alle cassette postali. Ciò avviene perché un processo denominato cassette postali di processi Assistente cartelle gestite ogni 7 giorni. Anziché attendere l'Assistente cartelle gestite per l'esecuzione, è possibile imporre a tale scopo, eseguire il cmdlet **Start-ManagedFolderAssistant** di Exchange Online PowerShell. 
  
 **Cosa succede quando si esegue l'Assistente cartelle gestite?** Le impostazioni nel criterio di conservazione applicato, controllare gli elementi nella cassetta postale e determinare se è soggetto a conservazione. Quindi inserisce gli elementi soggetti a conservazione con il tag di conservazione appropriati e quindi viene eseguita l'azione di conservazione specificato negli elementi oltre il periodo di conservazione. 
  
Di seguito sono i passaggi per la connessione a Exchange Online PowerShell e quindi eseguire l'Assistente cartelle gestite in tutte le cassette postali nell'organizzazione.
  
1. Nel computer locale, aprire Windows PowerShell ed eseguire il comando riportato di seguito.
    
    ```
    $UserCredential = Get-Credential
    ```

    Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell** digitare il nome utente e password per l'account amministratore globale di Office 365 e quindi fare clic su **OK**.
    
2. Eseguire il comando riportato di seguito.
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. Eseguire il comando riportato di seguito.
    
    ```
    Import-PSSession $Session
    ```

4. Per verificare di essere connessi alla propria organizzazione Exchange Online, eseguire il seguente comando per visualizzare un elenco di tutte le cassette postali dell'organizzazione:
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > Per ulteriori informazioni o se si riscontrano problemi di connessione per l'organizzazione Exchange Online, vedere [Connessione a Exchange Online tramite remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283). 
  
5. Eseguire i seguenti comandi per avviare l'Assistente cartelle gestite per tutte le cassette postali nell'organizzazione.
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Questo è tutto! Installazione di un criterio di archiviazione e l'eliminazione per l'organizzazione di neve accesso a terze parti.
  
## <a name="more-information"></a>Ulteriori informazioni
<a name="moreinfo"> </a>

- La modalità di calcolo periodo di conservazione? Il periodo di conservazione degli elementi della cassetta postale viene calcolato dalla data di consegna o data di creazione di elementi, ad esempio i messaggi bozza che non vengono inviati, ma vengono creati dall'utente. Quando l'Assistente cartelle gestite elabora elementi in una cassetta postale, contrassegna una data di inizio e data di scadenza di tutti gli elementi contenenti i tag di conservazione con l'azione di conservazione Elimina e Consenti ripristino o Elimina definitivamente. Gli elementi con un tag di archiviazione vengono contrassegnati con una move date. 
    
- Nella tabella seguente vengono fornite ulteriori informazioni su ogni tag di conservazione viene aggiunto il criterio di conservazione personalizzata che è stato creato seguendo i passaggi descritti in questo argomento.
    
    |**Tag di conservazione**|**Scopo di questo tag**|**Incorporata o personalizzata?**|**Type**|
    |:-----|:-----|:-----|:-----|
    |Accesso a terze parti neve 3 anni spostamento nell'archivio  <br/> |Sposta gli elementi da 1095 giorni (3 anni) la cassetta postale di archiviazione.  <br/> |Personalizzato (vedere [passaggio 2: creare nuovi tag di conservazione per i criteri di archiviazione e l'eliminazione](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )  <br/> |Tag criterio predefinito (archivio); Questo tag viene automaticamente applicato a dell'intera cassetta postale.  <br/> |
    |Accesso a terze parti neve anno 7 Elimina definitivamente  <br/> |Elimina definitivamente gli elementi nella cassetta postale di archiviazione o la cassetta postale principale quando sono 7 anni.  <br/> |Personalizzato (vedere [passaggio 2: creare nuovi tag di conservazione per i criteri di archiviazione e l'eliminazione](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )  <br/> |Tag criterio predefinito (eliminazione); Questo tag viene automaticamente applicato a dell'intera cassetta postale.  <br/> |
    |Accesso a terze parti neve eliminazione elementi 5 anni Elimina e Consenti ripristino  <br/> |Elimina gli elementi dalla cartella Posta eliminata vengono 5 anni. Gli utenti possono recuperare questi elementi di backup di 14 giorni dopo che viene eliminati.<sup>\*</sup> <br/> |Personalizzato (vedere [passaggio 2: creare nuovi tag di conservazione per i criteri di archiviazione e l'eliminazione](set-up-an-archive-and-deletion-policy-for-mailboxes.md#step3) )  <br/> |Tag criterio di conservazione (elementi eliminati); Questo tag viene automaticamente applicato agli elementi nella cartella elementi eliminati.  <br/> |
    |Giorni 14 elementi recuperabili Sposta nell'archivio  <br/> |Sposta gli elementi che sono stati nella cartella elementi ripristinabili 14 giorni nella cartella elementi recuperabili di cassetta postale di archivio.  <br/> |Incorporato  <br/> |Tag criterio di conservazione (elementi recuperabili); Questo tag viene automaticamente applicato agli elementi nella cartella elementi recuperabili.  <br/> |
    |Posta indesiderata  <br/> |Consente di eliminare definitivamente gli elementi che sono stati nella cartella posta indesiderata per 30 giorni. Gli utenti possono recuperare questi elementi di backup di 14 giorni dopo che viene eliminati.<sup>\*</sup> <br/> |Incorporato  <br/> |Tag criterio di conservazione (posta indesiderata); Questo tag viene automaticamente applicato agli elementi nella cartella posta indesiderata.  <br/> |
    |Elimina dopo 1 mese  <br/> |Consente di eliminare definitivamente gli elementi da 30 giorni. Gli utenti possono recuperare questi elementi di backup di 14 giorni dopo che viene eliminati.<sup>\*</sup> <br/> |Incorporato  <br/> |Personali; Questo tag può essere applicato dagli utenti.  <br/> |
    |Elimina dopo 1 anno  <br/> |Consente di eliminare definitivamente gli elementi da 365 giorni. Gli utenti possono recuperare questi elementi di backup di 14 giorni dopo che viene eliminati.<sup>\*</sup> <br/> |Incorporato  <br/> |Personali; Questo tag può essere applicato dagli utenti.  <br/> |
    |Non eliminare mai  <br/> |Questo tag impedire l'eliminazione per un criterio di conservazione degli elementi.  <br/> |Incorporato  <br/> |Personali; Questo tag può essere applicato dagli utenti.  <br/> |
    |Spostamento nell'archivio personale dopo 1 anno  <br/> |Sposta elementi la cassetta postale di archiviazione dopo 1 anno.  <br/> |Incorporato  <br/> |Personali; Questo tag può essere applicato dagli utenti.  <br/> |
   
    > <sup>\*</sup>Gli utenti possono utilizzare lo strumento Recupera elementi eliminati in Outlook e Outlook Web App per recuperare un elemento eliminato nel periodo di mantenimento elementi eliminati, che per impostazione predefinita è 14 giorni in Exchange Online. Un amministratore può utilizzare Windows PowerShell per aumentare il periodo di mantenimento elementi eliminati per un massimo di 30 giorni. Per ulteriori informazioni, vedere: [Recupera elementi eliminati in Outlook per Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) e [modificare il periodo di mantenimento elementi eliminati per una cassetta postale di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)
  
- Utilizzo di **recuperabili elementi 14 giorni Sposta nell'archivio** conservazione tag consente libero spazio di archiviazione nella cartella elementi ripristinabili nella cassetta postale principale dell'utente. Ciò è utile quando postale una cassetta viene messa in attesa, ciò significa che non sono mai definitivamente eliminato cassetta postale dell'utente. Senza spostare gli elementi la cassetta postale di archiviazione, è possibile che viene raggiunto la quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale principale. Per ulteriori informazioni su questa e per evitarlo, vedere [aumentare la quota per le cassette postali in attesa agli elementi ripristinabili](https://go.microsoft.com/fwlink/p/?LinkId=786479).
