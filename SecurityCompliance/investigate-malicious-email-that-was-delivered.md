---
title: Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Intelligence)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection: M365-security-compliance
description: Informazioni su come usare Threat Intelligence per individuare e studiare messaggi di posta elettronica dannosi.
ms.openlocfilehash: adf4066b5119f131b90dc88b99be4011582931c2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215496"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a>Individuare ed esaminare messaggi di posta elettronica dannosi recapitati (Office 365 Threat Intelligence)

[Office 365 Threat Intelligence](office-365-ti.md) consente di analizzare le attività che consentono agli utenti di eseguire operazioni per proteggere l'organizzazione. Ad esempio, se si fa parte del team di sicurezza dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati agli utenti. È possibile eseguire questa operazione utilizzando [Esplora minacce](get-started-with-ti.md#threat-explorer).
  
> [!IMPORTANT]
> A partire da febbraio 2019 e distribuita nei prossimi mesi, Office 365 Threat Intelligence sta diventando Office 365 Advanced Threat Protection Plan 2, con ulteriori funzionalità di protezione dalle minacce. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che vengano soddisfatti i seguenti requisiti:
  
- L'organizzazione dispone di [office 365 Threat Intelligence](office-365-ti.md) e [assegna licenze agli utenti in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
- La [registrazione di controllo di Office 365](turn-audit-log-search-on-or-off.md) è attivata per l'organizzazione. 
    
- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [gestione delle minacce nel centro sicurezza &amp; e conformità di Office 365](threat-management.md).
    
- Si è un amministratore globale di Office 365 oppure è stato assegnato l'amministratore della sicurezza o il ruolo di ricerca ed eliminazione nel centro sicurezza &amp; e conformità. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Gestione di messaggi di posta elettronica sospetti

Gli utenti malintenzionati possono inviare messaggi ai propri clienti per cercare di phishing le proprie credenziali e accedere ai segreti aziendali. Per evitare questo, è consigliabile utilizzare i servizi di protezione dalle minacce offerti da Office 365, tra cui Exchange Online Protection e Advanced Threat Protection. Tuttavia, è possibile che un utente malintenzionato invii messaggi di posta elettronica agli utenti che contengono un URL e solo in seguito fare in modo che l'URL punti a contenuto dannoso (malware e così via). In alternativa, si potrebbe rendersi conto che un utente dell'organizzazione è stato compromesso e che l'utente è stato compromesso, un aggressore ha utilizzato quell'account per inviare messaggi di posta elettronica ad altri utenti della propria azienda. Durante la pulizia di entrambi gli scenari, potrebbe essere necessario rimuovere i messaggi di posta elettronica dalle cassette postali degli utenti. In situazioni come queste, è possibile sfruttare Threat Explorer per individuare e rimuovere i messaggi di posta elettronica.
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Individuare ed eliminare messaggi di posta elettronica sospetti recapitati

> [!TIP]
> [Esplora minacce](get-started-with-ti.md#threat-explorer) (noto anche come esploratore), è un potente report che può servire a molteplici scopi, ad esempio la ricerca e l'eliminazione dei messaggi, l'identificazione dell'indirizzo IP di un mittente di posta elettronica dannoso o l'avvio di un incidente per ulteriori indagini. La procedura seguente si concentra sull'utilizzo di Esplora risorse per individuare ed eliminare messaggi di posta elettronica dannosi dalle cassette postali dei destinatari. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel riquadro di spostamento a sinistra, scegliere **gestione** \> **** minacce.
    
3. Scegliere **tutti i messaggi di posta elettronica**dal menu Visualizza.<br/>![Utilizzare il menu Visualizza per scegliere tra la posta elettronica e i rapporti di contenuto](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Si notino le etichette che vengono visualizzate nel report, **** ad esempio recapitate, **sconosciute**o recapitate in **posta**indesiderata.<br/>![Esplora minacce che mostra i dati per tutti i messaggi di posta](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>A seconda delle operazioni eseguite nei messaggi di posta elettronica per l'organizzazione, è possibile che vengano visualizzate altre etichette, ad esempio **bloccate** o **sostituite**.
    
5. Nel rapporto scegliere reCapitato per visualizzare solo i messaggi di posta elettronica che sono finiti nelle cassette postali degli utenti. ****<br/>![Se si fa clic su "reCapitato alla posta indesiderata", vengono rimossi](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Al di sotto del grafico, esaminare l'elenco di **posta elettronica** al di sotto del grafico.<br/>![Sotto il grafico, visualizzare un elenco di messaggi di posta elettronica che sono stati rilevati](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. Nell'elenco, scegliere un elemento per visualizzare ulteriori dettagli sul messaggio di posta elettronica. Ad esempio, è possibile fare clic sulla riga dell'oggetto per visualizzare le informazioni sul mittente, i destinatari, gli allegati e altri messaggi di posta elettronica simili.<br/>![È possibile visualizzare ulteriori informazioni su un elemento, inclusi i dettagli e gli allegati.](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. Dopo aver visualizzato le informazioni sui messaggi di posta elettronica, selezionare uno o più elementi nell'elenco per attivare **+ azioni**.
    
9. Utilizzare l'elenco **+ Actions** per applicare un'azione, ad esempio **Move to deleted** Items. Questo eliminerà i messaggi selezionati dalle cassette postali dei destinatari.<br/>![Quando si selezionano uno o più messaggi di posta elettronica, è possibile scegliere tra diverse azioni disponibili](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)
  
[Protezione contro le minacce in Office 365](protect-against-threats.md)
  
[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

