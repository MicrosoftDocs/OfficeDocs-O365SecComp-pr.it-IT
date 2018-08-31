---
title: Creare elenchi di mittenti attendibili per l’intera organizzazione o elenchi di mittenti bloccati in Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Se si desidera si consiglia di ricevere posta elettronica da un determinato mittente attendibili li e i messaggi, è possibile modificare l'elenco Consenti di un criterio di filtro posta indesiderata nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: a90679fc900ca5695904898af3627fc1900a8545
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003165"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>Creare elenchi di mittenti attendibili per l’intera organizzazione o elenchi di mittenti bloccati in Office 365
  
Se si desidera si consiglia di ricevere posta elettronica da un determinato mittente attendibili li e i messaggi, è possibile modificare l'elenco Consenti di un criterio di filtro posta indesiderata nell'interfaccia di amministrazione di Exchange (EAC) **protezione** \> **Filtro posta indesiderata**. Ulteriori informazioni su questo informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md). Un'altra opzione è necessario creare una regola di trasporto di Exchange che funziona come dominio o basata sugli utenti elenco Consenti del filtro posta indesiderata. È possibile bloccare i messaggi inviati da un determinato dominio o un utente in modo simile troppo.
  
Una regola di trasporto è utile in questa situazione se è necessario filtrare i criteri complessi, ad esempio controllo intestazioni del messaggio o i nomi di allegati o se si desidera aggiungere azioni complesse, ad esempio aggiungendo una dichiarazione di non responsabilità per il messaggio o l'applicazione di un periodo di tempo dove la rul f è attivo. Tuttavia, il metodo preferito per verificare che i messaggi di posta elettronica da un mittente specifico o dominio ignorare il filtro posta indesiderata è per aggiungerli ai criteri di filtro posta indesiderata. Introduzione a questo in EAC passando alla **protezione** \> **Filtro posta indesiderata**. Ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md).
  
> [!TIP]
> Dal momento che possono essere eseguito lo spoofing domini non è più protetto un elenco con indirizzo IP, un elenco basati sul dominio in una regola di trasporto. Inoltre, se l'indirizzo IP del mittente è un elenco di blocco, è comunque possibile bloccare anche se il filtro per il dominio o utente è stato escluso correttamente. Ciò avviene perché una regola di trasporto in un dominio o utente non sostituisce l'elenco indirizzi IP bloccati globale. È consigliabile utilizzare un elenco indirizzi IP basati sull'indirizzo nella maggior parte dei casi. Per creare un elenco di basati sull'indirizzo IP, è possibile utilizzare l'elenco indirizzi IP consentiti o un elenco di indirizzi IP bloccati nel filtro di connessione. I messaggi inviati da tali indirizzi IP non sono controllati dal filtro contenuto. Per istruzioni su come configurare il criterio di filtro di connessione tramite l'aggiunta di indirizzi IP per l'elenco indirizzi IP consentiti o un elenco di indirizzi IP bloccati, vedere [configurare il criterio di filtro di connessione](configure-the-connection-filter-policy.md). 
  
Per le attività di gestione aggiuntive relative alle regole di trasporto, vedere [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>Utilizzare EAC per personalizzare un blocco o consentire l'elenco impedire o ricezione della posta elettronica da un dominio o utente

1. In EAC, andare a **protezione** \> **Filtro posta indesiderata**. 
    
2. Nella pagina **Generale** , effettuare una delle operazioni seguenti: 
    
  - Fare doppio clic sul criterio predefinito o un criterio esistente per eseguirne la modifica.
    
  - Fare clic su **Nuovo** per creare un nuovo criterio di filtro posta indesiderata personalizzati che può essere applicato a utenti, gruppi e i domini nell'organizzazione. 
    
3. Nella pagina **Consentire elenchi** , è possibile specificare le voci, ad esempio i mittenti o domini che devono essere recapitati sempre la posta in arrivo. Posta elettronica da queste voci non viene elaborata dal filtro posta indesiderata. Eseguire le operazioni seguenti: 
    
  - Aggiungere i mittenti attendibili per il mittente elenco consentono. Fare clic su **Aggiungi**e quindi nella finestra di dialogo Selezione aggiungere gli indirizzi del mittente che si desidera consentire. È possibile separare più voci utilizzando un punto e virgola o una nuova riga. Fare clic su ok per tornare alla pagina **Consentire elenchi** . 
    
  - Aggiungere domini trusted al dominio elenco consentono. Fare clic su **Aggiungi**e quindi nella finestra di dialogo selezione, aggiungere i domini che si desidera consentire. È possibile separare più voci utilizzando un punto e virgola o una nuova riga. Fare clic su ok per tornare alla pagina **Consentire elenchi** . 
    
    > [!CAUTION]
    > Se si consentono domini di livello superiore, è probabile che la posta elettronica indesiderata sarà recapitata in una cartella di Posta in arrivo. 
  
4. Nella pagina **Elenchi contatti bloccati**, è possibile specificare voci, come mittenti o domini, che verranno sempre contrassegnati come Posta indesiderata. Il servizio applica l'azione di probabilità di posta indesiderata configurata alla posta elettronica che corrisponde a tali voci. 
    
  - Aggiungere i mittenti indesiderati all'elenco dei mittenti bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
    
  - Aggiungere i domini indesiderati all'elenco dei domini bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
    
    > [!CAUTION]
    > Se si bloccano domini di livello superiore, è probabile che la posta elettronica desiderata verrà contrassegnata come Posta indesiderata. 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-transport-rule"></a>Che cosa è necessario sapere prima di iniziare a creare una regola di trasporto
    
- Non è necessario creare una regola di trasporto per ignorare il filtro posta indesiderata o contrassegnare posta elettronica come posta indesiderata per un mittente o un dominio. Utilizzare il blocco di Exchange Online Protection e consentire elenchi in un criterio della posta indesiderata invece di questa regola di trasporto se si desidera bloccare o consentire un mittente specifico o un dominio e collegare eventuali ulteriori condizioni. Ulteriori informazioni su questo informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md).
    
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Regole di trasporto" nell'argomento [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx). 
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
    
> [!TIP]
> Problemi? Richiedere assistenza nei forum di Exchange. Visitare il forum in [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-the-eac-to-create-a-transport-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>Utilizzare EAC per creare una regola di trasporto per ignorare i filtri per un dominio o utente

1. In EAC, accedere a **flusso di posta** \> **regole**. Scegliere **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) e quindi fare clic su **Ignora filtro posta indesiderata**.
    
2. Assegnare un nome alla regola. In **Applica la regola se**, scegliere **Il mittente** quindi selezionare una delle seguenti condizioni: 
    
  - Se si desidera specificare un dominio, scegliere il **dominio è**. Nella finestra di dialogo **indicazione dominio** immettere il dominio del mittente che si desidera impostare come attendibili, ad esempio contoso.com. **Aggiungere** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) per spostarsi all'elenco di frasi. Se si desidera aggiungere ulteriori domini e fare clic su **OK** al termine, ripetere l'operazione. 
    
  - Se si desidera specificare un utente, scegliere **è questa persona**. Nella finestra di dialogo **Seleziona membri**, aggiungere l'utente dall'elenco o digitare l'utente, quindi fare clic su **Controlla nomi**. Ripetere la procedura per aggiungere ulteriori utenti e fare clic su **OK** una volta terminato. 
    
3. Selezionare la casella di controllo **arrestare l'elaborazione di più regole** per assicurarsi che nessun altra regola può essere annullate l'azione di bypass 
    
4. Per l'opzione **indirizzo mittente corrispondenza nel messaggio** , selezionare **intestazione o busta**.
    
5. Se si desidera, è possibile effettuare le selezioni per la regola di controllo, testare la regola, abilitare la regola di un periodo di tempo specifico e le altre selezioni. Si consiglia di verificare la regola per un periodo di tempo prima applicazione all'interno dell'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).
    
6. Scegliere **Salva** per salvare la regola. 
    
Dopo aver creato e applicato la regola, il filtro di protezione da posta indesiderata viene ignorato per il dominio o utente specificato.
  
## <a name="use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>Utilizzare EAC per creare una regola di trasporto che blocca i messaggi inviati da un dominio o utente

1. In EAC, accedere a **flusso di posta** \> **regole**. Scegliere **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) e quindi fare clic su **Crea una nuova regola**.
    
2. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**. 
    
3. In **Applica la regola se**, scegliere **Il mittente** quindi selezionare una delle seguenti condizioni: 
    
  - Se si desidera specificare un dominio, scegliere il **dominio è**. Nella finestra di dialogo dominio specifica, immettere il dominio del mittente da cui si desidera bloccare i messaggi, ad esempio contoso.com. Fare clic su **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) per spostarsi all'elenco di frasi. Se si desidera aggiungere ulteriori domini e fare clic su **OK** al termine, ripetere l'operazione. 
    
  - Se si desidera specificare un utente, scegliere **è questa persona**. Nella finestra di dialogo **Seleziona membri**, aggiungere l'utente dall'elenco o digitare l'utente, quindi fare clic su **Controlla nomi**. Ripetere la procedura per aggiungere ulteriori utenti e fare clic su **OK** una volta terminato. 
    
4. Sotto **Effettuare la seguente operazione**, scegliere **Blocca il messaggio** e fare clic su una delle altre opzioni, ad esempio **Elimina il messaggio senza inviare alcuna notifica**.
    
5. Fare clic su **altre opzioni**e quindi per l'opzione **indirizzo mittente corrispondenza nel messaggio** , selezionare **intestazione o busta**.
    
6. Se si desidera, è possibile effettuare le selezioni per la regola di controllo, testare la regola, abilitare la regola di un periodo di tempo specifico e le altre selezioni. Si consiglia di verificare la regola per un periodo di tempo prima applicazione all'interno dell'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).
    
7. Scegliere **Salva** per salvare la regola. 
    
Dopo aver creato a applicato la regola, i messaggi inviati dal dominio o dall'utente specificato saranno bloccati.
  
## <a name="see-also"></a>Vedere anche

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
[Utilizzare le regole di trasporto per configurare il filtro di posta elettronica in blocco](use-transport-rules-to-configure-bulk-email-filtering.md)

