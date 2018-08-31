---
title: Allegati Safe degli strumenti di analisi di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/03/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: La caratteristica allegati sicuri consente di verificare momento del clic allegati di posta elettronica. Utilizzare gli allegati sicuri per proteggere l'organizzazione da utenti malintenzionati file inviare o ricevere posta elettronica.
ms.openlocfilehash: 0a28923bff8aa2cd987159edd3cad77ed42f80f4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530799"
---
# <a name="office-365-atp-safe-attachments"></a>Allegati Safe degli strumenti di analisi di Office 365

Gli allegati sicuri degli strumenti di analisi (con [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md)) fa parte di [Protezione di Office 365 avanzate rischio](office-365-atp.md) (degli strumenti di analisi). La caratteristica allegati sicuri degli strumenti di analisi consente di verificare se gli allegati di posta elettronica sono dannosi e quindi esegue un'operazione per proteggere l'organizzazione. La caratteristica allegati sicuri degli strumenti di analisi consente di proteggere l'organizzazione in base ai [criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md) impostati dagli amministratori della protezione globali di Office 365. 
  
A partire in ritardo 2018 marzo e varie settimane successivo, protezione degli strumenti di analisi viene esteso per i file in SharePoint Online, OneDrive for Business e Teams Microsoft. Per ulteriori informazioni, vedere [Office 365 avanzate Threat Protection for SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md).
       
## <a name="how-it-works"></a>Funzionamento

La caratteristica allegati sicuri degli strumenti di analisi controlla gli allegati di posta elettronica per gli utenti nell'organizzazione. Quando un criterio di allegati sicuri degli strumenti di analisi è sul posto e un utente a cui che criteri Visualizza il messaggio di posta elettronica in Office 365, vengono controllati gli allegati di posta elettronica e vengono intraprese azioni appropriate, basato su criteri di allegati sicuri degli strumenti di analisi. A seconda di come vengono definiti i criteri, le persone possono continuare a lavorare senza mai conoscere che sono stati inviati file dannosi.
  
Di seguito sono due esempi di allegati sicuri degli strumenti di analisi in ufficio.
  
- **Esempio 1: allegato di posta elettronica** Si supponga che Lee riceve un messaggio di posta elettronica contenente un allegato. Non è ovvio Lee fatto che allegato attendibili o effettivamente contiene malware progettato per sottrarre le credenziali utente di Lee. Organizzazione di Lee, un amministratore della sicurezza definito un criterio di allegati sicuri degli strumenti di analisi pochi giorni. Con la caratteristica allegati sicuri degli strumenti di analisi, allegato di posta elettronica viene aperto e test rigorosi in un ambiente virtuale prima che li riceve Lee. Se l'allegato è determinata da dannoso, verranno rimossi automaticamente. Se l'allegato è sicuro, verrà aperto nel modo previsto quando Lee fa clic su di esso. 
    
- **Con l'esempio 2: File in SharePoint Online** Si supponga di Jean ricevuto un file caricato in una raccolta di SharePoint Online. Jean condivide il collegamento al file con altri membri del team, senza sapere che il file è effettivamente dannoso. Fortunatamente, [degli strumenti di analisi di SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md) rileva il file dannoso e si blocca. Pochi giorni dopo, Chris passa per aprire il documento. Sebbene Chris possono visualizzare che il file esiste, non possono aprire o condividerlo, impedendo computer Chris e altri file dannoso Chris. 
    
Gli allegati sicuri degli strumenti di analisi criteri possono essere applicati a specifici utenti o gruppi all'interno dell'organizzazione o per l'intero dominio. Per ulteriori informazioni, vedere **[impostazione dei criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md)**. 
  
## <a name="how-to-get-atp-safe-attachments"></a>Come ottenere gli allegati sicuri degli strumenti di analisi

La caratteristica allegati sicuri degli strumenti di analisi fa parte di avanzate di rischio protezione, è incluso in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, avanzate Threat Protection può essere acquistato come componente aggiuntivo. (Come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).
  
La caratteristica allegati sicuri degli strumenti di analisi si applica quando:
  
- Vengono impostati i criteri gli allegati sicuri degli strumenti di analisi. Vedere [impostazione dei criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md).
    
- Gli utenti hanno effettuato l'accesso a Office 365 utilizzando il proprio account di lavoro o della scuola. Vedere [accesso a Office o Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Come sapere se protezione gli allegati sicuri degli strumenti di analisi è sul posto

 [Criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md) deve essere definita nell'ordine indicato per la protezione degli allegati sicuri degli strumenti di analisi in locale. 
  
Un modo efficace per vedere come funziona il servizio è visualizzando i [report per la protezione avanzata di rischio](view-reports-for-atp.md).
  
Inoltre, nella tabella seguente vengono descritti alcuni scenari di esempio. In tutti i casi, si presuppone che l'organizzazione dispone di Office 365 Enterprise E5, che include una protezione avanzata di rischio.
  
|**Scenario di esempio**|**Protezione gli allegati sicuri degli strumenti di analisi si applica in questo caso?**|
|:-----|:-----|
|Organizzazione di PAT ha E5 Enterprise di Office 365, ma non è definita ancora tutti i criteri per gli allegati sicuri degli strumenti di analisi.  <br/> |No. Sebbene la funzionalità è disponibile, almeno un criterio di allegati sicuri degli strumenti di analisi deve essere definito nell'ordine indicato per la protezione degli allegati sicuri degli strumenti di analisi in locale.  <br/> |
|Lee è un dipendente del reparto vendite presso Contoso. Organizzazione di Lee contiene un criterio di allegati sicuri degli strumenti di analisi sul posto a cui si applica solo ai dipendenti finance.  <br/> |No. In questo caso, i dipendenti finance avrebbe protezione gli allegati sicuri degli strumenti di analisi, ma altri dipendenti, tra cui il reparto vendito, potrebbe non fino a quando non vengono definiti i criteri che includono tali gruppi.  <br/> |
|Nel giorno precedente, un amministratore di Office 365 all'organizzazione di Jean configurare un criterio di allegati sicuri degli strumenti di analisi che si applica a tutti i dipendenti. In precedenza oggi Jean ricevuto un messaggio di posta elettronica contenente un allegato.  <br/> |Sì. In questo esempio Jean dispone di una licenza per la protezione avanzata di rischio e un criterio di allegati sicuri degli strumenti di analisi che include Jean è stato definito. In genere necessario circa 30 minuti per un nuovo criterio rendere effettive tra datacenter; Poiché un giorno trascorsa in questo caso, il criterio deve essere attivo.  <br/> |
|Organizzazione di Chris contiene E5 Enterprise di Office 365 con i criteri degli strumenti di analisi provvisoria allegati sul posto per tutti gli utenti nell'organizzazione. Chris riceve un messaggio di posta elettronica che ha un allegato e inoltra il messaggio ad altri utenti che si trovano all'esterno dell'organizzazione.  <br/> |Protezione gli allegati sicuri degli strumenti di analisi è sul posto per i messaggi che riceve Chris. Nel caso le organizzazioni i destinatari anche i criteri degli strumenti di analisi provvisoria allegati sul posto, il messaggio viene inoltrata Chris sarà soggetta a quei criteri quando si riceve il messaggio inoltrato.  <br/> |
|Organizzazione Elena ha i criteri degli strumenti di analisi provvisoria allegati sul posto [degli strumenti di analisi di SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md) è stata attivata. Chiara si presuppone che ogni file in SharePoint Online è stati analizzati e sia aprire o scaricare.<br/> |Protezione gli allegati sicuri degli strumenti di analisi è sul posto in base ai criteri definiti; Tuttavia, ciò significa che viene eseguita l'analisi di ogni singolo file in SharePoint Online, OneDrive for Business o Teams Microsoft. (Per ulteriori informazioni, vedere [degli strumenti di analisi di SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md)).<br/> |
   
## <a name="submitting-files-for-malware-analysis"></a>Invio di file per l'analisi antimalware

Se si riceve un file che si desidera richiedere a Microsoft di analizzare, visitare il sito [per invio a un file per l'analisi di malware](https://aka.ms/wdsi/submit).
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Impostare i criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md)
  
[Collegamenti degli strumenti di analisi sicuro in Office 365](atp-safe-links.md)
  
[Le funzionalità di anti-phishing ATP in Office 365](atp-anti-phishing.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)
  

