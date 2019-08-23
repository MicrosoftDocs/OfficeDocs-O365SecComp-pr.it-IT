---
title: Individuare e studiare messaggi di posta elettronica dannosi che sono stati recapitati in Office 365, TIMailData-inline, incidenti di sicurezza, incidenti, ATP PowerShell, malware per la posta elettronica, utenti compromessi, phishing di posta elettronica, malware della posta elettronica, leggere intestazioni di posta, leggere intestazioni, aprire intestazioni
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Informazioni su come utilizzare le funzionalità di analisi e risposta alle minacce per individuare e studiare messaggi di posta elettronica dannosi.
ms.openlocfilehash: 25eb1f4a13ad698d7b6817ea7917ccabea7210ae
ms.sourcegitcommit: f473bf7f215ba4eb2f49e0dd23a9d2e39fa512c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "36566224"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>Individuare e studiare messaggi di posta elettronica dannosi che sono stati recapitati in Office 365

[Office 365 Advanced Threat Protection](office-365-atp.md) consente di analizzare le attività che consentono agli utenti di eseguire operazioni per proteggere l'organizzazione. Ad esempio, se si fa parte del team di sicurezza dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati agli utenti. A tale scopo, è possibile utilizzare [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che vengano soddisfatti i seguenti requisiti:
  
- L'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) e le [licenze vengono assegnate agli utenti](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- La [registrazione di controllo di Office 365](turn-audit-log-search-on-or-off.md) è attivata per l'organizzazione. 
    
- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [protezione dalle minacce in Office 365](protect-against-threats.md).
    
- Si è un amministratore globale di Office 365 oppure è stato assegnato l'amministratore della sicurezza o il ruolo di ricerca ed eliminazione nel centro sicurezza &amp; e conformità. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Gestione di messaggi di posta elettronica sospetti

Gli utenti malintenzionati possono inviare messaggi ai propri clienti per cercare di phishing le proprie credenziali e accedere ai segreti aziendali. Per evitare questo, è consigliabile utilizzare i servizi di protezione dalle minacce in Office 365, tra cui [Exchange Online Protection](eop/exchange-online-protection-overview.md) e [Advanced Threat Protection](office-365-atp.md). Tuttavia, è possibile che un utente malintenzionato invii messaggi di posta elettronica agli utenti che contengono un URL e solo in seguito fare in modo che l'URL punti a contenuto dannoso (malware e così via). 

In alternativa, si potrebbe rendersi conto che un utente dell'organizzazione è stato compromesso e che l'utente è stato compromesso, un aggressore ha utilizzato quell'account per inviare messaggi di posta elettronica ad altri utenti della propria azienda. Durante la pulizia di entrambi gli scenari, potrebbe essere necessario rimuovere i messaggi di posta elettronica dalle cassette postali degli utenti. In situazioni come queste, è possibile sfruttare le [minacce Explorer (o rilevamenti in tempo reale)](threat-explorer.md) per individuare e rimuovere tali messaggi di posta elettronica.

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>Dove si trovano i messaggi di posta elettronica reindirizzati dopo aver eseguito le operazioni

In che modo i messaggi di posta elettronica problematici passano e quali strumenti aiutano gli investigatori a capire cosa gli è successo? I campi di Esplora minacce segnalano informazioni che consentono agli amministratori di decodificare gli eventi di posta elettronica problematici.

### <a name="view-the-email-headers-and-download-the-email-body"></a>Visualizzare le intestazioni di posta elettronica e scaricare il corpo del messaggio di posta elettronica

**L'anteprima dell'intestazione del messaggio di posta elettronica e il download del corpo della posta** elettronica sono utili funzionalità di gestione delle minacce di posta elettronica disponibili in minacce. Gli amministratori saranno in grado di analizzare e scaricare intestazioni e messaggi di posta elettronica per le minacce. L'accesso per l'utilizzo di questa funzionalità è controllato dal controllo di accesso basato sui ruoli (RBAC), per ridurre il rischio di esposizione dei contenuti della posta elettronica degli utenti.

È necessario aggiungere un nuovo *ruolo*denominato ' Preview ' in un altro gruppo di ruoli di Office 365, ad esempio nelle operazioni sec o nell'amministratore sec, per garantire la possibilità di scaricare i messaggi di posta elettronica e le intestazioni di anteprima nella visualizzazione all-mail.

Per visualizzare il riquadro a comparsa con le opzioni per il download e l'anteprima dell'intestazione di posta elettronica: 

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel riquadro di spostamento a sinistra, scegliere **gestione** \> **** minacce.

3. Fare clic su un oggetto nella tabella Esplora minacce.

Verrà aperto il riquadro a comparsa, in cui sono posizionati sia l'anteprima dell'intestazione che i collegamenti di download della posta elettronica.

> [!IMPORTANT]
> Utilizzare entrambe le tabelle che seguono insieme. Uno indica che il controllo RBAC è necessario, l'altro, il percorso in cui devono essere concessi i diritti.
<p>

|Attività  |RoleGroup RBAC con accesso |È necessario il ruolo ' Preview '?  |
|---------|---------|---------|
|Utilizzo di Esplora minacce (e rilevamenti in tempo reale) per l'analisi delle minacce     |  Amministratore globale di Office 365<br> Amministratore della sicurezza, <br> Lettore di sicurezza      | No   |
|Utilizzare Esplora minacce (e rilevamenti in tempo reale) per visualizzare le intestazioni per i messaggi di posta elettronica e visualizzare in anteprima e scaricare messaggi di posta elettronica in quarantena    |     Amministratore globale di Office 365 <br> Amministratore della sicurezza, <br>Lettore di sicurezza    |       No  |
|Utilizzare Esplora minacce per visualizzare intestazioni e scaricare messaggi di posta elettronica recapitati alle cassette postali     |      Amministratore globale di Office 365 <br>Amministratore della sicurezza,<br> Lettore di sicurezza, <br> Anteprima    |   Sì      |

<br>

|RoleGroup RBAC  |Cui vengono assegnati gli utenti  |
|---------|---------|
| Amministratore globale   | Interfaccia di amministrazione di Office 365        |
| Amministratore della sicurezza      |    Centro sicurezza e conformità     |
| Lettore di sicurezza   |    Centro sicurezza e conformità     |
|      |    Centro sicurezza e conformità     |


> [!CAUTION]
> Tenere presente che ' Preview ' è un ruolo e non un RoleGroup e che tale ruolo deve essere aggiunto successivamente a un RoleGroup.

![Riquadro a comparsa di Esplora minacce con collegamenti per il download e l'anteprima nella pagina.](media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> Questa funzionalità non viene visualizzata per i messaggi di posta elettronica che non sono mai stati trovati nella cassetta postale di un utente, che può verificarsi se un messaggio di posta elettronica è stato eliminato o se il recapito non è Nei casi in cui i messaggi di posta elettronica sono stati eliminati dalle cassette postali degli utenti, gli amministratori visualizzeranno un errore che indica che la posta non è stata trovata.

### <a name="check-the-delivery-action-and-location"></a>Controllare l'azione e il percorso di recapito

I rilevamenti in tempo reale di Esplora minacce sono stati aggiunti i campi azione di recapito e posizione di recapito nel luogo dello stato del recapito. Questo comporta un'immagine più completa della posizione dei messaggi di posta elettronica. Parte dell'obiettivo di questa modifica è facilitare la ricerca per gli addetti alle operazioni di sicurezza, ma il risultato finale è la conoscenza del percorso dei messaggi di posta elettronica problematici.

Lo stato di recapito è ora suddiviso in due colonne:

- **Azione** di recapito-qual è lo stato di questo messaggio di posta elettronica?
- **Percorso** di recapito-dove è stato instradato il messaggio di posta elettronica come risultato?

Azione di recapito è l'azione intrapresa su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

- **** Recapitato: la posta elettronica è stata recapitata alla posta in arrivo o alla cartella di un utente e l'utente può accedervi direttamente.
- **Junked** – la posta elettronica è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella posta indesiderata o eliminata.
- **Bloccato** : tutti i messaggi di posta elettronica in quarantena, che non sono riusciti o sono stati eliminati. Questo è completamente inaccessibile dall'utente.
- **Sostituito** – qualsiasi messaggio di posta elettronica in cui gli allegati dannosi sono stati sostituiti dai file. txt che affermano che l'allegato è dannoso
 
Il percorso di recapito consente di visualizzare i risultati dei criteri e i rilevamenti eseguiti dopo il recapito. È collegato a un'azione di recapito. Questo campo è stato aggiunto per fornire informazioni dettagliate sull'azione intrapresa quando viene trovata una posta elettronica problematica. Di seguito sono riportati i possibili valori del percorso di recapito:

- **Posta in arrivo o cartella** – la posta elettronica è in posta in arrivo o in una cartella (in base alle regole di posta elettronica).
- **On-Prem o External** -la cassetta postale non esiste sul cloud ma è in locale.
- **Cartella** posta indesiderata: l'indirizzo di posta elettronica nella cartella posta indesiderata di un utente.
- **Cartella** posta eliminata: il messaggio nella cartella elementi eliminati di un utente.
- **Quarantine** : l'indirizzo di posta elettronica in quarantena e non è incluso nella cassetta postale di un utente.
- **Failed** : la posta elettronica non è riuscita a raggiungere la cassetta postale.
- **Eliminato** : il messaggio di posta elettronica viene perso da qualche parte nel flusso.

### <a name="view-the-timeline-of-your-email"></a>Visualizzare la sequenza temporale del messaggio di posta elettronica
  
 **Timeline del messaggio di posta elettronica** un altro campo in Threat Explorer prevedrà anche la ricerca più facile per gli amministratori. Invece di passare del tempo prezioso a controllare dove potrebbe essere andato il messaggio di posta elettronica, quando, durante l'analisi di un evento, quando si verificano più eventi in un messaggio di posta elettronica o vicino allo stesso tempo, tali eventi verranno visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito alla posta verranno acquisiti nella colonna '*Special Action*'. La combinazione delle informazioni dalla sequenza temporale della posta con l'azione speciale intrapresa sul post-recapito della posta dà agli amministratori informazioni sui criteri e sulla gestione delle minacce, ad esempio la posizione in cui il messaggio è stato instradato e, in alcuni casi, la valutazione finale.

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Individuare ed eliminare messaggi di posta elettronica sospetti recapitati

> [!TIP]
> Esplora minacce (a volte denominato Esplora) è un report potente che può servire a più scopi, ad esempio la ricerca e l'eliminazione dei messaggi, l'identificazione dell'indirizzo IP di un mittente di posta elettronica dannoso o l'avvio di un incidente per ulteriori indagini. La procedura seguente si concentra sull'utilizzo di Esplora risorse per individuare ed eliminare messaggi di posta elettronica dannosi dalle cassette postali dei destinatari.

Per visualizzare le modifiche apportate al precedente campo stato di recapito (ora operazione di recapito e posizione di recapito): 

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel riquadro di spostamento a sinistra, scegliere **gestione** \> **** minacce.


![Esplora minacce con i campi azione di recapito e posizione di recapito.](media/ThreatExFields.PNG)

È possibile notare la nuova colonna ' Special actions ' in questo elemento grafico. Questa funzionalità ha lo scopo di informare gli amministratori sull'esito dell'elaborazione di un messaggio di posta elettronica. Le azioni speciali possono essere aggiornate alla fine della *sequenza temporale della posta elettronica*di Threat Explorer, che è una nuova funzionalità che consente di migliorare l'esperienza di ricerca per gli amministratori.

La sequenza temporale della posta elettronica riduce la randomizzazione perché è necessario meno tempo per controllare posizioni diverse per cercare di comprendere gli eventi accaduti dopo l'arrivo del messaggio di posta elettronica. Quando più eventi si verificano in un messaggio di posta elettronica o vicino allo stesso tempo, gli eventi vengono visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito alla posta verranno acquisiti nella colonna ' azioni speciali '. La combinazione delle informazioni provenienti dalla cronologia della posta *elettronica* di quel messaggio con le *azioni speciali* intraprese nel post-recapito della posta darà agli amministratori informazioni su come funzionano i propri criteri, in cui la posta è stata definitivamente instradata e, in alcuni casi, quali sono le ultime la valutazione è stata. È possibile accedere alla colonna azioni speciali nello stesso luogo in cui si trova l'operazione di recapito e il percorso di recapito, ma per visualizzare una sequenza temporale della posta elettronica:

1. Fare clic sull'oggetto del messaggio di posta elettronica.
2. Nel riquadro visualizzato, fare clic su *sequenza temporale della posta elettronica*. (Apparirà tra le altre intestazioni del pannello come ' Riepilogo ' o ' dettagli ', eccetera).

Dopo aver aperto la sequenza temporale della posta elettronica, dovrebbe essere visualizzata una tabella in cui vengono illustrati gli eventi dopo il recapito della posta o, nel caso di nessun altro evento per il messaggio di posta elettronica, si dovrebbe vedere un singolo appuntamento per il recapito originale che diventerà un risultato come *bloccato* con un verdetto come *phishing*. La scheda ha anche la possibilità di esportare l'intera sequenza temporale della posta elettronica e in questo modo verranno esportati tutti i dettagli nella scheda e nei dettagli del messaggio di posta elettronica (elementi quali Subject, sender, Recipient, Network e Message ID).

3. Scegliere **tutti i messaggi di posta elettronica**dal menu Visualizza.<br/>![Utilizzare il menu Visualizza per scegliere tra la posta elettronica e i rapporti di contenuto](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Si notino le etichette che vengono visualizzate nel report, **** ad esempio recapitate, **sconosciute**o recapitate in **posta**indesiderata.<br/>![Esplora minacce che mostra i dati per tutti i messaggi di posta](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>A seconda delle operazioni eseguite nei messaggi di posta elettronica per l'organizzazione, è possibile che vengano visualizzate altre etichette, ad esempio **bloccate** o **sostituite**.
    
5. Nel rapporto scegliere recapitato per visualizzare solo i messaggi di posta elettronica che sono finiti nelle cassette postali degli utenti. ****<br/>![Se si fa clic su "recapitato alla posta indesiderata", vengono rimossi](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Al di sotto del grafico, esaminare l'elenco di **posta elettronica** al di sotto del grafico.<br/>![Sotto il grafico, visualizzare un elenco di messaggi di posta elettronica che sono stati rilevati](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. Nell'elenco, scegliere un elemento per visualizzare ulteriori dettagli sul messaggio di posta elettronica. Ad esempio, è possibile fare clic sulla riga dell'oggetto per visualizzare le informazioni sul mittente, i destinatari, gli allegati e altri messaggi di posta elettronica simili.<br/>![È possibile visualizzare ulteriori informazioni su un elemento, inclusi i dettagli e gli allegati.](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. Dopo aver visualizzato le informazioni sui messaggi di posta elettronica, selezionare uno o più elementi nell'elenco per attivare **+ azioni**.
    
9. Utilizzare l'elenco **+ Actions** per applicare un'azione, ad esempio **Move to deleted** Items. Questo eliminerà i messaggi selezionati dalle cassette postali dei destinatari.<br/>![Quando si selezionano uno o più messaggi di posta elettronica, è possibile scegliere tra diverse azioni disponibili](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection piano 2](office-365-ti.md)
  
[Protezione dalle minacce in Office 365](protect-against-threats.md)
  
[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

