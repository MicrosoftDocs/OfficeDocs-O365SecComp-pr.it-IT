---
title: Consente di creare avvisi attività in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: Aggiungere e gestire gli avvisi di impegno nella protezione &amp; centro conformità in modo da Office 365 verranno inviate notifiche email quando gli utenti eseguono attività specifiche in Office 365.
ms.openlocfilehash: 409c1ff4c7fdd0d2d071bdb2eab08ec49357ed8a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531193"
---
# <a name="create-activity-alerts-in-the-office-365-security-amp-compliance-center"></a>Consente di creare avvisi attività in Office 365 Security &amp; centro conformità

È possibile creare un avviso di attività che invierà una notifica tramite posta elettronica quando gli utenti eseguono attività specifiche in Office 365. Gli avvisi di attività sono simili a ricerca per gli eventi nel Registro di controllo di Office 365, ad eccezione del fatto che è verrà inviato un messaggio di posta elettronica quando per un'attività che è stato creato un avviso per un evento si verifica. 
  
 **Perché utilizzare avvisi attività anziché la ricerca nel Registro di controllo?** Potrebbero verificarsi determinati tipi di attività o eseguite dagli utenti specifici che si desiderano conoscere. Invece di ricordare la ricerca nel Registro di controllo per tali attività, è possibile utilizzare gli avvisi di attività per inviare un messaggio di posta elettronica quando gli utenti eseguono le attività di Office 365. Ad esempio, è possibile creare un avviso di attività per ricevere una notifica quando un utente elimina i file di SharePoint oppure è possibile creare un avviso per ricevere una notifica quando un utente consente di eliminare definitivamente i messaggi dalla cassetta postale. La notifica di posta elettronica inviata a un utente sono incluse informazioni sulle attività che è stata eseguita e l'utente che ha eseguito lo. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Deve essere assegnato il ruolo di configurazione dell'organizzazione in sicurezza &amp; centro conformità per gestire gli avvisi di attività. Per impostazione predefinita, questo ruolo viene assegnato a gruppi di ruoli amministratore di conformità e la gestione dell'organizzazione. Per ulteriori informazioni sull'aggiunta di membri a gruppi di ruoli, vedere [fornire agli utenti di accedere a Office 365 Security &amp; centro conformità](grant-access-to-the-security-and-compliance-center.md).
    
- Utente (o un'altra amministrazione) necessario attivare la registrazione di controllo per l'organizzazione prima di iniziare a utilizzare gli avvisi di attività. A tale scopo, fare clic su **Avvia registrazione utente e all'attività amministratore** nella pagina **avvisi attività** . (Se non viene visualizzato questo collegamento, il controllo è già stato attivato per la propria organizzazione.) Può inoltre attivare il controllo della pagina **ricerca dei registri di controllo** della sicurezza &amp; centro conformità (andare a **ricerca &amp; indagini** \> **ricerca dei registri di controllo**). È necessario eseguire questa operazione una sola volta per l'organizzazione.
    
- È possibile utilizzare la pagina **avvisi** di sicurezza &amp; centro conformità per creare gli avvisi solo per le attività eseguite dagli utenti che sono elencati nella rubrica dell'organizzazione. È possibile utilizzare questa pagina per creare gli avvisi per le attività eseguite dagli utenti esterni. 
    
- Visualizzare le [informazioni](#more-information) di sezione per un elenco di scenari comuni (attività specifiche per monitorare e) che è possibile creare avvisi per. 
    
- È possibile creare avvisi per le stesse attività che è possibile cercare nel Registro di controllo di Office 365. 
    
## <a name="create-an-activity-alert"></a>Creare un avviso di attività

1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro fare clic su **avvisi**e quindi fare clic su **Gestisci avvisi**.
    
4. Nella pagina **avvisi attività** fare clic su **Aggiungi un avviso**.
    
    ![Aggiungere un avviso di attività](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
5. Completare i campi seguenti per creare un avviso:
    
    r. **Name** - digitare un nome per l'avviso. I nomi degli avvisi deve essere univoci all'interno dell'organizzazione.
    
    b. **Descrizione** (facoltativo) - viene illustrata l'avviso, ad esempio le attività e gli utenti si tiene traccia, e gli utenti che le notifiche di posta elettronica inviati a. Descrizioni offrono un modo semplice e veloce per descrivere lo scopo dell'avviso per gli altri amministratori.
    
    c. **inviare questo avviso quando** - fare clic su **Invia quando questo avviso** e quindi configurare questi due campi:
    
    - **Attività** - fare clic sull'elenco a discesa elenco per visualizzare le attività che è possibile creare un avviso per. Questo è lo stesso elenco di attività che viene visualizzato quando si esegue una ricerca nel Registro di controllo di Office 365. È possibile selezionare uno o più attività specifiche oppure è possibile scegliere il nome del gruppo di attività per selezionare tutte le attività nel gruppo. Per una descrizione di queste attività, vedere la sezione "Possibile controllare le attività" della funzionalità di [ricerca il controllo di accesso nel centro conformità protezione di Office 365](search-the-audit-log-in-security-and-compliance.md#audited-activities). Quando un utente esegue una qualsiasi delle attività di aggiunta all'avviso, viene inviata una notifica tramite posta elettronica. 
    
     - **Gli utenti** , fare clic su questa casella e quindi selezionare uno o più utenti. Se gli utenti in questa casella di eseguire le attività che è stato aggiunto alla casella **delle attività** , verrà inviato un avviso. Lasciare vuoto per inviare un avviso quando tutti gli utenti nell'organizzazione esegue le attività specificate dall'avviso casella **utenti** . 
    
    **Invia avviso a** - d. fare clic su **Invia avviso**, quindi fare clic sulla casella **destinatari** e digitare un nome per aggiungere un utenti che riceveranno una notifica tramite posta elettronica quando un utente (specificato nella casella **utenti** ) esegue un'attività (specificato nel Finestra di **attività** ). Si noti che si viene aggiunti all'elenco dei destinatari per impostazione predefinita. È possibile rimuovere il nome dall'elenco.
    
6. Fare clic su **Salva** per creare l'avviso. 
    
    Il nuovo avviso viene visualizzato nell'elenco nella pagina **avvisi attività** . 
    
    ![Nella pagina attività gli avvisi di sicurezza viene visualizzato un elenco di avvisi &amp; centro conformità](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    Lo stato dell'avviso è impostato **su**. Si noti che vengono elencati anche i destinatari che verrà ricevuto una notifica tramite posta elettronica quando viene inviato un avviso. 
  
## <a name="turn-off-an-activity-alert"></a>Disattivare un avviso di attività

È possibile disattivare un avviso di attività in modo che non viene inviata una notifica di posta elettronica. Dopo la disattivazione dell'avviso di attività, viene comunque visualizzato nell'elenco degli avvisi di attività per l'organizzazione ed è comunque possibile visualizzare le relative proprietà.
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro fare clic su **avvisi**e quindi fare clic su **Gestisci avvisi attività**.
    
4. Nell'elenco degli avvisi per la propria organizzazione, fare clic sull'avviso che si desidera disattivare.
    
5. Nella pagina **Modifica avviso** fare clic su disattivazione **in** per modificare lo stato per **disattivare**e quindi fare clic su **Salva**.
    
    Lo stato dell'avviso nelle pagine di avvisi attività è impostato su **Off**. 
    
Per attivare un avviso di attività, ripetere questi passaggi e fare clic su disattivazione **disattivato** per modificare lo stato di **attivato**.
  
## <a name="more-information"></a>Ulteriori informazioni

- Di seguito è riportato un esempio della notifica di posta elettronica inviato agli utenti specificati in inviati a questo avviso al campo (ed elencati in **destinatari** nella pagina **attività avvisi** ) per la protezione &amp; centro conformità. 
    
    ![Esempio di Notification un messaggio di posta elettronica inviato per un avviso di attività](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Vengono di seguito alcune attività comuni di documenti e posta elettronica che è possibile creare un'attività degli avvisi per. Le tabelle vengono descritte le attività, il nome dell'attività per creare un avviso per e il nome del gruppo di attività che è elencato all'interno dell'attività nell'elenco a discesa **delle attività** . Per visualizzare un elenco completo delle attività che è possibile creare avvisi attività per, vedere la sezione "Possibile controllare le attività" della funzionalità di [ricerca il controllo di accesso nel centro conformità protezione di Office 365](search-the-audit-log-in-security-and-compliance.md#audited-activities).
    
    > [!TIP]
    > È possibile creare un avviso di attività per una sola attività che viene eseguita da un utente. Oppure è possibile creare un avviso di attività per tenere traccia delle attività più eseguite da uno o altri utenti. 
  
    Nella tabella seguente sono elencate alcune attività comuni relativi ai documenti di SharePoint o OneDrive for Business.
    
    |**Quando un utente esegue questa operazione...**|**Creare un avviso per l'attività**|**Gruppo di attività**|
    |:-----|:-----|:-----|
    |Visualizza un documento in un sito.  <br/> |File a cui si accede  <br/> |Attività di file e cartelle  <br/> |
    |Modifica o modifica di un documento.  <br/> |File modificato  <br/> |Attività di file e cartelle  <br/> |
    |Condivide un documento con un utente esterno all'organizzazione.  <br/> |Condivisione file, cartelle o sito  <br/> E  <br/> Creazione di invito alla condivisione  <br/> Per ulteriori informazioni, vedere [utilizzo di condivisione controllo nel Registro di controllo di Office 365](use-sharing-auditing.md).  <br/> |Attività di richiesta di condivisione e accesso  <br/> |
    |Caricare o scaricare un documento.  <br/> |File caricato  <br/> E/o  <br/> File scaricato  <br/> |Attività di file e cartelle  <br/> |
    |Modifica le autorizzazioni di accesso a un sito.  <br/> |Autorizzazioni sito modificato  <br/> |Attività di amministrazione sito  <br/> |

    Nella tabella seguente sono elencate alcune attività comuni relative alla posta elettronica in Exchange Online.

    |**Quando un utente esegue questa operazione...**|**Creare un avviso per l'attività**|**Gruppo di attività**|
    |:-----|:-----|:-----|
    |In modo permanente (Elimina) consente di eliminare un messaggio di posta elettronica di messaggi dalla cassetta postale.  <br/> |Messaggi eliminati dalla cassetta postale  <br/> | Attività delle cassette postali di Exchange  <br/> |
    |Invia un messaggio di posta elettronica da una cassetta postale condivisa.  <br/> |Utilizzo di autorizzazioni Invia come messaggio è stato inviato  <br/> E  <br/> Utilizzo di autorizzazioni Invia per conto di messaggio è stato inviato  <br/> | Attività delle cassette postali di Exchange  <br/> |
   
- È inoltre possibile utilizzare i cmdlet **New-ActivityAlert** e **Set-ActivityAlert** in sicurezza &amp; PowerShell centro conformità per creare e modificare gli avvisi di attività. Se si utilizzano questi cmdlet per creare o modificare gli avvisi di attività, tenere presenti i seguenti aspetti: 
    
  - Se si utilizza un cmdlet per aggiungere un'attività di avviso che non sia elencato nell'elenco a discesa **delle attività** , viene visualizzato un messaggio nella pagina delle proprietà per l'avviso che informa che, "questo avviso contiene operazioni personalizzate non è elencate in selezione". 
    
  - Strettamente necessario utilizzare i cmdlet per creare o modificare un avviso attività consiste nell'inviare notifiche tramite posta elettronica a una persona esterna all'organizzazione. L'utente esterno verrà elencato nell'elenco dei destinatari dell'avviso. Ma se si rimuove l'utente esterno dall'avviso, l'utente non può essere nuovamente aggiunto all'avviso utilizzando la pagina **Modifica avviso** in sicurezza &amp; centro conformità. Sarà necessario aggiungere di nuovo l'utente esterno utilizzando il cmdlet **Set-ActivityAlert** o utilizzare il cmdlet **New-ActivityAlert** per aggiungere l'utente esterno stesso (o diverso) a un nuovo avviso. 
    
  

