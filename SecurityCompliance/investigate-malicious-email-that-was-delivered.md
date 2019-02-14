---
title: Trovare e analizzare dannoso posta elettronica che è stato recapitato (Business Intelligence rischio di Office 365)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection: M365-security-compliance
description: Informazioni su come utilizzare Intelligence minaccia per trovare e provare a utilizzare e-mail dannoso.
ms.openlocfilehash: c7492ccf2a7fa5d67b256264c6ed6fbdb06bcbc8
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995187"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a>Trovare e analizzare dannoso posta elettronica che è stato recapitato (Business Intelligence rischio di Office 365)

[Business Intelligence di Office 365 rischio](office-365-ti.md) consente di analizzare le attività che inserire gli utenti a rischio ed eseguire un'azione per proteggere l'organizzazione. Ad esempio, se si fa parte del team di protezione dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati agli utenti. È possibile eseguire questo tramite [Esplora rischio](get-started-with-ti.md#threat-explorer).
  
> [!IMPORTANT]
> A partire da febbraio 2019 e distribuzione sui prossimi mesi, Business Intelligence di Office 365 rischio sta diventando Office 365 avanzate Threat Protection piano 2, le funzionalità di protezione aggiuntive rischio. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che vengano soddisfatti i seguenti requisiti:
  
- L'organizzazione dispone di [Business Intelligence di Office 365 rischio](office-365-ti.md) e [assegnare licenze agli utenti di Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
- [Registrazione di controllo di Office 365](turn-audit-log-search-on-or-off.md) è attivata per la propria organizzazione. 
    
- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [management in Office 365 protezione delle minacce &amp; centro conformità](threat-management.md).
    
- Essere un amministratore globale di Office 365 o si dispone di amministratore della sicurezza o il ruolo di ricerca ed eliminazione assegnato nella protezione &amp; centro conformità. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
    
## <a name="dealing-with-suspicious-emails"></a>Gestione di messaggi di posta elettronica sospetti

Malintenzionati potrebbe essere l'invio dei messaggi a utenti di prova e per attività di phishing le proprie credenziali e accedere ai segreti aziendali! Per evitare questo problema, è consigliabile utilizzare i servizi di protezione di rischio offerti da Office 365, inclusi Exchange Online Protection e protezione da minacce avanzate. Tuttavia, vi sono alcuni quando un utente malintenzionato inviare posta elettronica per gli utenti che contiene un URL e solo in seguito apportare tale punto URL al contenuto dannoso (malware e così via). In alternativa, è possibile realizzare troppo avanzata che un utente nell'organizzazione è stato danneggiato e mentre l'utente è stata danneggiata, un utente malintenzionato utilizzato tale account per l'invio di posta elettronica ad altri utenti all'interno della società. Come parte di pulizia entrambi i casi, è possibile rimuovere i messaggi di posta elettronica dalla posta in arrivo utente. In situazioni di questo tipo, è possibile utilizzare Explorer minaccia per trovare e rimuovere i messaggi di posta elettronica!
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Cercare ed eliminare messaggi sospetti è stato recapitato

> [!TIP]
> [Soluzioni di rischio](get-started-with-ti.md#threat-explorer) (anche noto come Explorer), è un referente potente che può avere diversi scopi, ad esempio ricerca e l'eliminazione dei messaggi, che identifica l'indirizzo IP del mittente messaggio di posta elettronica dannoso o avvio di un evento imprevisto per un'analisi più approfondita. La procedura seguente viene illustrato l'utilizzo di soluzioni per trovare ed eliminare dannoso posta elettronica dalle cassette postali di destinatari. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. Verrà visualizzata la sicurezza &amp; centro conformità. 
    
2. Nel riquadro di spostamento sinistro, scegliere **gestione rischio** \> **Explorer**.
    
3. Nel menu Visualizza, scegliere **tutta la posta elettronica**.<br/>![Utilizzare il menu Visualizza di scegliere tra report contenuto e di posta elettronica](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Osservare le etichette vengono visualizzati nel rapporto, ad esempio **recapitati**, **sconosciuto**o **recapitato alla posta indesiderata**.<br/>![Soluzioni di rischio la visualizzazione di dati per tutta la posta elettronica](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(A seconda delle azioni intraprese nei messaggi di posta elettronica per l'organizzazione, è possibile vedere etichette aggiuntive, ad esempio **bloccato** o **è stata sostituita**).
    
5. Nel rapporto, scegliere **recapitati** per visualizzare solo i messaggi di posta elettronica fine posta in arrivo degli utenti.<br/>![Fare clic su "Recapitato alla posta indesiderata" consente di rimuovere tali dati dalla visualizzazione](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Sotto il grafico, esaminare l'elenco di **posta elettronica** di sotto del grafico.<br/>![Sotto il grafico, visualizzare un elenco di messaggi di posta elettronica che sono stati rilevati](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. Nell'elenco, selezionare una voce per visualizzare ulteriori dettagli su tale messaggio di posta elettronica. Ad esempio, è possibile fare clic su riga dell'oggetto per visualizzare informazioni su mittente, i destinatari, gli allegati e altri messaggi di posta elettronica simile.<br/>![È possibile visualizzare ulteriori informazioni su un elemento, inclusi i dettagli e degli allegati](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. Dopo la visualizzazione delle informazioni sui messaggi di posta elettronica, selezionare uno o più elementi nell'elenco per attivare **+ Azioni**.
    
9. Utilizzare l'elenco **+ Azioni** per applicare un'azione, ad esempio **Sposta di eliminazione** elementi. Verranno eliminati i messaggi selezionati dalle cassette postali dei destinatari.<br/>![Quando si selezionano una o più messaggi di posta elettronica, è possibile scegliere tra diverse azioni disponibili](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)
  
[Protezione contro le minacce in Office 365](protect-against-threats.md)
  
[Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)
  

