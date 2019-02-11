---
title: Utilizzare le regole di flusso di posta elettronica per configurare la posta elettronica in blocco il filtro in Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: Gli amministratori possono imparare a utilizzare le regole di flusso di posta in Exchange Online Protection per il filtro di posta elettronica in blocco.
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382807"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Utilizzare le regole di flusso di posta elettronica per configurare la posta elettronica in blocco il filtro in Exchange Online Protection

È possibile impostare filtri contenuti a livello aziendale per la posta elettronica da posta indesiderata e blocco tramite i criteri di filtro contenuto posta indesiderata predefiniti. Vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md) e [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) su come impostare i criteri di filtro dei contenuti. 
  
Se si desidera altre opzioni per filtrare i messaggi in blocco, è possibile creare le regole di flusso di posta elettronica (noto anche come regole di trasporto) per cercare i modelli di testo o frasi domande presenti in messaggi di posta elettronica in blocco. Qualsiasi messaggio che include le seguenti caratteristiche verrà contrassegnato come posta indesiderata. Utilizzo di queste regole consentono di ridurre la quantità di posta elettronica in blocco che riceve l'organizzazione.
  
**Note**:

- Prima di creazione di regole di flusso della posta descritte in questo argomento, è consigliabile leggere innanzitutto [Qual è la differenza tra posta indesiderata e posta elettronica in blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [i valori di massa reclamo livello](bulk-complaint-level-values.md). 
  
- Le procedure seguenti messaggio è contrassegnato come posta indesiderata per l'intera organizzazione. Tuttavia, è possibile aggiungere un'altra condizione per queste regole si applicano solo a destinatari specifici dell'organizzazione. In questo modo, il posta elettronica in blocco aggressivo possono applicare le impostazioni del filtro per alcuni utenti altamente mirate, mentre il resto degli utenti (gli utenti che per la maggior parte ricevono il posta elettronica in blocco che vengono iscritti) non sono interessate. 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Creare una regola del flusso di posta elettronica per filtrare i messaggi di posta elettronica in blocco in base agli schemi di testo

1. Nell'interfaccia di amministrazione di Exchange accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.
    
3. Specificare un nome per la regola.
    
4. Fare clic su **altre opzioni**. In **Applica questa regola se**, selezionare **l'oggetto o nel corpo** \> **oggetto o nel corpo corrisponde a questi modelli di testo**.
    
5. Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti espressioni regolari che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine: 
    
   - Se non è possibile visualizzare il contenuto di questo messaggio di posta elettronica\,
    
   - \\>(safe )?unsubscribe( here)?\\</a\\>
    
   - Se non si desidera ricevere ulteriori comunicazioni di questo tipo\,
    
   - \\<img height\="?1"? width\="?1"? src\=.?http\://
    
   - Per non ricevere più questi\s+messaggi di posta elettronica\:http\://
    
   - Per annullare la sottoscrizione a \w+ (e\-?letter|e?-?mail|newsletter)
    
   - no longer (wish )?(to )?(be sent|receive) \w+ email
    
   - Se non è possibile visualizzare il contenuto di questo messaggio di posta elettronica\, fare clic qui
    
   - Per essere sicuri di ricevere (your daily deals|our e-?mails)\, aggiungere
    
   - Se non si desidera più ricevere questi messaggi di posta elettronica
    
   - per modificare le (subscription preferences|preferences or unsubscribe)
    
   - fare clic (here to|the) annullare la sottoscrizione
    
   **Note**:

   - Tale elenco non è un set completo di espressioni regolari di messaggi di posta elettronica in blocco, informazioni possono essere aggiunti o rimossi in base alle esigenze. È tuttavia un punto di partenza ottimale.
    
   - Cercare parole o modelli di testo nell'oggetto o gli altri campi dell'intestazione nel messaggio viene generato *dopo che* il messaggio è stato decodificato dal trasferimento di contenuto MIME codifica del metodo utilizzato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. È possibile utilizzare le condizioni o eccezioni per cercare il raw (in genere Base64) codificato i valori dell'oggetto o gli altri campi dell'intestazione nei messaggi. 
    
6. In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.
    
7. Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.
    
   L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
    
   > [!NOTE]
   > Se l'azione configurato il messaggio di quarantena anziché di inviarlo alla cartella posta indesiderata i destinatari, il messaggio verrà inviato per la quarantena amministratore come la corrispondenza di una regola di flusso di posta elettronica e non sarà disponibile nella quarantena della posta indesiderata utente finale o tramite per l'utente finale notifiche di posta indesiderata. 
  
   Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).
    
8. Salvare la regola.
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Creare una regola del flusso di posta elettronica per filtrare i messaggi di posta elettronica in blocco in base alle frasi

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.
    
2. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.
    
3. Specificare un nome per la regola.
    
4. Fare clic su **altre opzioni**. In **Applica questa regola se**, selezionare **l'oggetto o nel corpo** \> **oggetto o nel corpo include una di queste parole**.
    
5. Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti frasi che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine: 
    
   - per modificare le preferenze o annullare la sottoscrizione
    
   - Modificare le preferenze di posta elettronica o annullare la sottoscrizione
    
   - Questo è un messaggio di posta elettronica promozionale
    
   - Hai ricevuto questo messaggio di posta elettronica perché hai richiesto una sottoscrizione
    
   - fare clic qui per annullare la sottoscrizione
    
   - Hai ricevuto questo messaggio di posta elettronica perché hai effettuato la sottoscrizione
    
   - Se non si desidera più ricevere la nostra newsletter
    
   - per annullare la sottoscrizione a questa newsletter
    
   - Se si verificano dei problemi nella visualizzazione di questo messaggio di posta elettronica
    
   - Questo è un annuncio pubblicitario
    
   - si desidera annullare la sottoscrizione o modificare
    
   - visualizzare questo messaggio di posta elettronica come pagina Web
    
   - Hai ricevuto questo messaggio di posta elettronica perché hai effettuato la sottoscrizione
    
   **Nota**: ancora una volta, l'elenco non è un set completo di frasi di messaggi di posta elettronica in blocco, informazioni possono essere aggiunti o rimossi in base alle esigenze. È tuttavia un punto di partenza ottimale.
    
6. In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.
    
7. Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.
    
   L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).
    
   > [!NOTE]
   > Se l'azione configurato il messaggio di quarantena anziché di inviarlo alla cartella posta indesiderata i destinatari, il messaggio verrà inviato per la quarantena amministratore come la corrispondenza di una regola di flusso di posta elettronica e non sarà disponibile nella quarantena della posta indesiderata utente finale o tramite per l'utente finale notifiche di posta indesiderata. 
  
   Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).

8. Salvare la regola.

## <a name="for-more-information"></a>Ulteriori informazioni

[Differenza tra posta elettronica indesiderata e posta elettronica in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Valori al livello reclamo massa](bulk-complaint-level-values.md)

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)

[Opzioni di filtro della posta indesiderata](advanced-spam-filtering-asf-options.md)
