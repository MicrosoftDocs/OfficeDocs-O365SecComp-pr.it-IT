---
title: Creare elenchi di mittenti attendibili o bloccati per l'intera organizzazione in Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Se si vuole essere sicuri di ricevere la posta da un mittente specifico, poiché si considera attendibile l'elenco dei messaggi consentiti in un criterio di filtro posta indesiderata nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: 4731fe4a72a3c331725b82e09240e6af91bb6afd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153728"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>Creare elenchi di mittenti attendibili o bloccati per l'intera organizzazione in Office 365
  
Se si desidera essere sicuri di ricevere la posta da un mittente specifico, poiché si considera attendibili i messaggi, è possibile modificare l'elenco Consenti in un criterio di filtro di posta indesiderata nell'interfaccia di amministrazione di Exchange (EAC) al filtro **protezione** \> da **posta**indesiderata. Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata. Un'altra opzione consiste nella creazione di una regola del flusso di posta di Exchange (nota anche come regola di trasporto) che funziona come l'elenco di domini o Consenti basato sull'utente nel filtro posta indesiderata. È possibile bloccare anche i messaggi inviati da un determinato dominio o utente in modo analogo.
  
Una regola del flusso di posta sarebbe utile in questa situazione se è necessario filtrare criteri complessi, ad esempio controllare le intestazioni dei messaggi o i nomi degli allegati o se si desidera aggiungere azioni complesse, ad esempio l'aggiunta di una dichiarazione di non responsabilità al messaggio o l'applicazione di un periodo di tempo in cui il RUL e attivo. Tuttavia, il metodo preferito per assicurarsi che i messaggi di posta elettronica provenienti da un mittente o da un dominio specifico ignorino il filtro per la posta indesiderata è di aggiungerli al criterio di filtro Per iniziare a utilizzare questa operazione nell'interfaccia di amministrazione di Exchange, andare a **protezione** \> dalla **posta**indesiderata. Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata.
  
> [!TIP]
> Un elenco basato sul dominio in una regola del flusso di posta non è protetto come un elenco basato sull'indirizzo IP, perché i domini possono essere falsificati. Inoltre, se l'indirizzo IP di invio è presente nell'elenco degli indirizzi bloccati, sarà comunque bloccato anche se viene ignorato il filtro del dominio o dell'utente. Ciò è dovuto al fatto che una regola del flusso di posta in un dominio o un utente non sovrascrive l'elenco di indirizzi IP bloccati globale. Si consiglia di utilizzare un elenco basato sull'indirizzo IP in gran parte dei casi. Per creare un elenco basato sull'indirizzo IP, è possibile utilizzare l'elenco di indirizzi IP consentiti o bloccati del filtro connessioni. I messaggi inviati da questi indirizzi IP non vengono controllati dal filtro contenuto. Per istruzioni su come configurare il criterio di filtro delle connessioni aggiungendo indirizzi IP all'elenco o all'elenco IP consentiti, vedere [Configure the Connection Filter Policy](configure-the-connection-filter-policy.md). 
  
Per altre attività di gestione relative alle regole del flusso di posta, vedere [Mail Flow Rules (Transport Rules) in Exchange Online](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per personalizzare un blocco o un elenco Consenti per impedire o ricevere messaggi di posta elettronica da un dominio o utente

1. Nell'interfaccia di amministrazione di Exchange, andare a filtro **protezione** \> da **posta**indesiderata. 
    
2. Nella pagina **generale** eseguire una delle operazioni seguenti: 
    
  - Fare doppio clic sul criterio predefinito o su un criterio esistente per iniziare a modificarlo.
    
  - Fare clic su **nuovo** per creare un nuovo criterio di filtro di posta indesiderata personalizzato che può essere applicato a utenti, gruppi e domini dell'organizzazione. 
    
3. Nella pagina degli **elenchi di indirizzi consentiti**, è possibile specificare voci, come mittenti e domini, ai quali verranno sempre recapitati messaggi di posta elettronica nella Posta in arrivo. La posta elettronica proveniente da tali voci non viene elaborata dal filtro di protezione da posta indesiderata. Eseguire le operazioni seguenti: 
    
  - Aggiungere i mittenti attendibili a Elenco mittenti consentiti. Fare clic su **Aggiungi**e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera consentire. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su OK per tornare alla pagina degli **elenchi elementi consentiti**. 
    
  - Aggiungere i domini attendibili a Elenco di domini consentiti. Fare clic su **Aggiungi**, quindi nella finestra di dialogo di selezione, aggiungere i domini che si desidera consentire. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su OK per tornare alla pagina degli **elenchi elementi consentiti**. 
    
    > [!CAUTION]
    > Se si consentono domini di livello superiore, è probabile che la posta elettronica indesiderata sarà recapitata in una cartella di Posta in arrivo. 
  
4. Nella pagina **Elenchi contatti bloccati**, è possibile specificare voci, come mittenti o domini, che verranno sempre contrassegnati come Posta indesiderata. Il servizio applica l'azione di probabilità di posta indesiderata configurata alla posta elettronica che corrisponde a tali voci. 
    
  - Aggiungere i mittenti indesiderati all'elenco dei mittenti bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
    
  - Aggiungere i domini indesiderati all'elenco dei domini bloccati. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **OK** per tornare alla pagina degli **elenchi di indirizzi bloccati**. 
    
    > [!CAUTION]
    > Se si bloccano domini di livello superiore, è probabile che la posta elettronica desiderata verrà contrassegnata come Posta indesiderata. 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-mail-flow-rule"></a>Che cosa è necessario sapere prima di iniziare a creare una regola del flusso di posta elettronica?
    
- Non è necessario creare una regola del flusso di posta per ignorare il filtro posta indesiderata o contrassegnare la posta elettronica come posta indesiderata per un mittente o dominio. Utilizzare Exchange Online Protection Block e consentire gli elenchi in un criterio di posta indesiderata invece che in questa regola del flusso del messaggio se si desidera semplicemente bloccare o consentire un mittente o un dominio specifico e non collegare eventuali condizioni aggiuntive. Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta](configure-your-spam-filter-policies.md)indesiderata.
    
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "regole del flusso di posta" nell'argomento [criteri di messaggistica e autorizzazioni di conformità](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) . 
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. Visitare i forum di Exchange [Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta elettronica per ignorare il filtro posta indesiderata per un dominio

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**. Fare **** ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona e quindi scegliere **Ignora filtro posta**indesiderata.
    
2. Assegnare un nome alla regola. In **Applica la regola se**, scegliere **Il mittente** quindi selezionare una delle seguenti condizioni: 
    
  - Se si desidera specificare un dominio, scegliere **il dominio è**. Nella finestra di dialogo **Specifica dominio**, immettere il dominio del mittente da designare come sicuro, ad esempio contoso.com. **Aggiungi** ![Aggiungere un'](media/ITPro-EAC-AddIcon.gif) icona per spostarla nell'elenco delle frasi. Ripetere la procedura per aggiungere ulteriori domini e fare clic su **OK** una volta terminato. 
    
  - Se si desidera specificare un utente, scegliere **è questa persona**. Nella finestra di dialogo **Seleziona membri**, aggiungere l'utente dall'elenco o digitare l'utente, quindi fare clic su **Controlla nomi**. Ripetere la procedura per aggiungere ulteriori utenti e fare clic su **OK** una volta terminato. 
    
3. Selezionare la casella di controllo Interrompi l' **elaborazione di altre regole** per assicurarsi che nessun'altra regola possa annullare l'azione di bypass 
    
4. Per l' **indirizzo del mittente della corrispondenza nell'** opzione del messaggio, selezionare **intestazione o busta**.
    
5. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni.
    
6. Scegliere **Salva** per salvare la regola. 
    
Dopo aver creato e applicato la regola, il filtro di protezione da posta indesiderata viene ignorato per il dominio o utente specificato.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta che blocchi i messaggi inviati da un dominio o utente

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**. Scegliere **Aggiungi** ![icona](media/ITPro-EAC-AddIcon.gif) e quindi fare clic su **Crea una nuova regola**.
    
2. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**. 
    
3. In **Applica la regola se**, scegliere **Il mittente** quindi selezionare una delle seguenti condizioni: 
    
  - Se si desidera specificare un dominio, scegliere **il dominio è**. Nella casella di dialogo Specifica dominio, immettere il dominio del mittente da cui si desidera bloccare i messaggi, ad esempio contoso.com. Fare **** ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per spostarlo nell'elenco delle frasi. Ripetere la procedura per aggiungere ulteriori domini e fare clic su **OK** una volta terminato. 
    
  - Se si desidera specificare un utente, scegliere **è questa persona**. Nella finestra di dialogo **Seleziona membri**, aggiungere l'utente dall'elenco o digitare l'utente, quindi fare clic su **Controlla nomi**. Ripetere la procedura per aggiungere ulteriori utenti e fare clic su **OK** una volta terminato. 
    
4. Sotto **Effettuare la seguente operazione**, scegliere **Blocca il messaggio** e fare clic su una delle altre opzioni, ad esempio **Elimina il messaggio senza inviare alcuna notifica**.
    
5. Fare clic su **altre opzioni**e quindi selezionare **intestazione o busta**per l' **indirizzo del mittente corrispondente nell'opzione messaggio** .
    
6. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un determinato periodo di tempo prima di applicarla all'interno dell'organizzazione.
    
7. Scegliere **Salva** per salvare la regola. 
    
Dopo aver creato a applicato la regola, i messaggi inviati dal dominio o dall'utente specificato saranno bloccati.
  
## <a name="see-also"></a>Vedere anche

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
[Usare le regole del flusso di posta per configurare il filtro per i messaggi inviati in blocco](use-transport-rules-to-configure-bulk-email-filtering.md)

