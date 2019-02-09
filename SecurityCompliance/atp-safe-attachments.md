---
title: Allegati Safe degli strumenti di analisi di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/08/2019
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: La caratteristica allegati sicuri consente di verificare momento del clic allegati di posta elettronica. Utilizzare gli allegati sicuri per proteggere l'organizzazione da utenti malintenzionati file inviare o ricevere posta elettronica.
ms.openlocfilehash: 45cd3b74b67d7ff8735da7a703ff14c4c517341f
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792231"
---
# <a name="office-365-atp-safe-attachments"></a>Allegati Safe degli strumenti di analisi di Office 365

## <a name="overview-of-office-365-atp-safe-attachments"></a>Panoramica di Office 365 degli strumenti di analisi Safe allegati

Gli allegati sicuri degli strumenti di analisi (con [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md)) fa parte di [Protezione di Office 365 avanzate rischio](office-365-atp.md) (degli strumenti di analisi). La caratteristica allegati sicuri degli strumenti di analisi consente di verificare se gli allegati di posta elettronica sono dannosi e quindi esegue un'operazione per proteggere l'organizzazione. La caratteristica allegati sicuri degli strumenti di analisi consente di proteggere l'organizzazione in base ai [criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md) impostati dagli amministratori della protezione globali di Office 365. 
  
Protezione degli strumenti di analisi può anche esteso per i file in SharePoint Online, OneDrive for Business e Teams Microsoft. Per ulteriori informazioni, vedere [Office 365 avanzate Threat Protection for SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md).
       
## <a name="how-it-works"></a>Funzionamento

La caratteristica allegati sicuri degli strumenti di analisi controlla gli allegati di posta elettronica per gli utenti nell'organizzazione. Quando un criterio di allegati sicuri degli strumenti di analisi è sul posto e un utente a cui che criteri Visualizza il messaggio di posta elettronica in Office 365, vengono controllati gli allegati di posta elettronica e vengono intraprese azioni appropriate, basato su criteri di allegati sicuri degli strumenti di analisi. A seconda di come vengono definiti i criteri, le persone possono continuare a lavorare senza mai conoscere che sono stati inviati file dannosi.
  
Di seguito sono due esempi di allegati sicuri degli strumenti di analisi in ufficio.
  
- **Esempio 1: allegato di posta elettronica** Si supponga che Lee riceve un messaggio di posta elettronica contenente un allegato. Non è ovvio Lee fatto che allegato attendibili o effettivamente contiene malware progettato per sottrarre le credenziali utente di Lee. Organizzazione di Lee, un amministratore della sicurezza definito un criterio di allegati sicuri degli strumenti di analisi pochi giorni. Con la caratteristica allegati sicuri degli strumenti di analisi, allegato di posta elettronica viene aperto e test rigorosi in un ambiente virtuale prima che li riceve Lee. Se l'allegato è determinata da dannoso, verranno rimossi automaticamente. Se l'allegato è sicuro, verrà aperto nel modo previsto quando Lee fa clic su di esso. 
    
- **Con l'esempio 2: File in SharePoint Online** Si supponga di Jean ricevuto un file caricato in una raccolta di SharePoint Online. Jean condivide il collegamento al file con altri membri del team, senza sapere che il file è effettivamente dannoso. Fortunatamente, [degli strumenti di analisi di SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md) rileva il file dannoso e si blocca. Pochi giorni dopo, Chris passa per aprire il documento. Sebbene Chris possono visualizzare che il file esiste, non possono aprire o condividerlo, impedendo computer Chris e altri file dannoso Chris. 
    
Gli allegati sicuri degli strumenti di analisi analisi abbia effettuare nella stessa area in cui si trovano i dati di Office 365. Per ulteriori informazioni sulle aree di centro dati, vedere [dove sono i dati si trova?](https://products.office.com/where-is-your-data-located?geo=All) 

Gli allegati sicuri degli strumenti di analisi criteri possono essere applicati a specifici utenti o gruppi all'interno dell'organizzazione o per l'intero dominio. Inoltre, gli allegati sicuri degli strumenti di analisi criteri possono essere configurati per utilizzare gli allegati segnaposto mentre vengono analizzati allegati effettivi. Per ulteriori informazioni, vedere **[impostazione dei criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md)**. 
  
## <a name="how-to-get-atp-safe-attachments"></a>Come ottenere gli allegati sicuri degli strumenti di analisi

Per prima cosa, verificare che la sottoscrizione include [Avanzate Threat Protection](office-365-atp.md). Degli strumenti di analisi è incluso in sottoscrizioni, ad esempio [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), E5 Enterprise di Office 365, Office 365 Education A5 e così via. Se l'organizzazione dispone di una sottoscrizione a Office 365 che non include degli strumenti di analisi di Office 365, è possibile acquistare potenzialmente degli strumenti di analisi come componente aggiuntivo. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 

Successivamente, verificare che i criteri degli strumenti di analisi gli allegati sicuri sono definiti. (Vedere [impostazione dei criteri di sicurezza allegati di Office 365 degli strumenti di analisi](set-up-atp-safe-attachments-policies.md)) Gli allegati sicuri degli strumenti di analisi caratteristiche siano attive quando:
  
- Vengono impostati i criteri gli allegati sicuri degli strumenti di analisi. Vedere [impostazione dei criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md).
    
- Gli utenti hanno effettuato l'accesso a Office 365 utilizzando il proprio account di lavoro o della scuola. Vedere [accesso a Office o Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).

Per definire o modificare i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito:

|Ruolo  |Modalità assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organization Management |Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Come sapere se protezione gli allegati sicuri degli strumenti di analisi è sul posto

Dopo avere [definito (o esaminato) i criteri di allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md), visualizzando i [report per la protezione avanzata di rischio](view-reports-for-atp.md)è un modo efficace per vedere come funziona il servizio.
  
Nella tabella seguente vengono descritti alcuni scenari di esempio. In tutti i casi, si presuppone che l'organizzazione dispone di una sottoscrizione a Office 365 che include una protezione avanzata di rischio.
  
|**Scenario di esempio**|**Protezione gli allegati sicuri degli strumenti di analisi si applica in questo caso?**|
|:-----|:-----|
|Organizzazione di PAT ha E5 Enterprise di Office 365, ma non è definita ancora tutti i criteri per gli allegati sicuri degli strumenti di analisi.  <br/> |No. Sebbene la funzionalità è disponibile, almeno un criterio di allegati sicuri degli strumenti di analisi deve essere definito nell'ordine indicato per la protezione degli allegati sicuri degli strumenti di analisi in locale.  <br/> |
|Lee è un dipendente del reparto vendite presso Contoso. Organizzazione di Lee contiene un criterio di allegati sicuri degli strumenti di analisi sul posto a cui si applica solo ai dipendenti finance.  <br/> |No. In questo caso, i dipendenti finance avrebbe protezione gli allegati sicuri degli strumenti di analisi, ma altri dipendenti, tra cui il reparto vendito, potrebbe non fino a quando non vengono definiti i criteri che includono tali gruppi.  <br/> |
|Nel giorno precedente, un amministratore di Office 365 all'organizzazione di Jean configurare un criterio di allegati sicuri degli strumenti di analisi che si applica a tutti i dipendenti. In precedenza oggi Jean ricevuto un messaggio di posta elettronica contenente un allegato.  <br/> |Sì. In questo esempio Jean dispone di una licenza per la protezione avanzata di rischio e un criterio di allegati sicuri degli strumenti di analisi che include Jean è stato definito. In genere necessario circa 30 minuti per un nuovo criterio rendere effettive tra datacenter; Poiché un giorno trascorsa in questo caso, il criterio deve essere attivo.  <br/> |
|Organizzazione di Chris contiene E5 Enterprise di Office 365 con i criteri degli strumenti di analisi provvisoria allegati sul posto per tutti gli utenti nell'organizzazione. Chris riceve un messaggio di posta elettronica che ha un allegato e inoltra il messaggio ad altri utenti che si trovano all'esterno dell'organizzazione.  <br/> |Protezione gli allegati sicuri degli strumenti di analisi è sul posto per i messaggi che riceve Chris. Nel caso le organizzazioni i destinatari anche i criteri degli strumenti di analisi provvisoria allegati sul posto, il messaggio viene inoltrata Chris sarà soggetta a quei criteri quando si riceve il messaggio inoltrato.  <br/> |
|Organizzazione Elena ha i criteri degli strumenti di analisi provvisoria allegati sul posto [degli strumenti di analisi di SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md) è stata attivata. Chiara si presuppone che ogni file in SharePoint Online è stati analizzati e sia aprire o scaricare.<br/> |Protezione gli allegati sicuri degli strumenti di analisi è sul posto in base ai criteri definiti; Tuttavia, ciò significa che viene eseguita l'analisi di ogni singolo file in SharePoint Online, OneDrive for Business o Teams Microsoft. (Per ulteriori informazioni, vedere [degli strumenti di analisi di SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md)).<br/> |
   
## <a name="submitting-files-for-malware-analysis"></a>Invio di file per l'analisi antimalware

- Se si riceve un file che si desidera richiedere a Microsoft di analizzare, visitare il sito [per invio a un file per l'analisi di malware](https://aka.ms/wdsi/submit).

- Se viene visualizzato un messaggio di posta elettronica, con o senza un allegato, che si desidera inviare a Microsoft per l'analisi, utilizzare [componente aggiuntivo di report](enable-the-report-message-add-in.md).
  
