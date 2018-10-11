---
title: Funzionalità di anti-phishing ATP in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: Protezione anti-phishing degli strumenti di analisi è disponibile come parte di protezione di Office 365 avanzate rischio. Anti-phishing degli strumenti di analisi si applica un insieme di modelli di apprendimento automatica insieme ad algoritmi di rilevamento di rappresentazione per i messaggi in arrivo per fornire la protezione per gli attacchi di phishing merce e spear. Tutti i messaggi sono soggetti a un'ampia gamma di modelli di apprendimento addestrati per rilevare i messaggi di phishing, insieme a un insieme di algoritmi avanzati utilizzati per la protezione da attacchi di rappresentazione utente e domini diversi. Protezione anti-phishing degli strumenti di analisi consente di proteggere l'organizzazione in base a criteri che sono impostati dagli amministratori della protezione globali di Office 365.
ms.openlocfilehash: e7bb4c4a28109c40bf745a25c9c8366558cf2ac7
ms.sourcegitcommit: ba2175e394d0cb9f8ede9206aabb44b5b677fa0a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496890"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Funzionalità di anti-phishing ATP in Office 365

Protezione anti-phishing degli strumenti di analisi è disponibile come parte di [Protezione di Office 365 avanzate rischio](https://technet.microsoft.com/en-us/library/exchange-online-advanced-threat-protection-service-description.aspx). Anti-phishing degli strumenti di analisi si applica un insieme di modelli di apprendimento automatica insieme ad algoritmi di rilevamento di rappresentazione per i messaggi in arrivo per fornire la protezione per gli attacchi di phishing merce e spear. Tutti i messaggi sono soggetti a un'ampia gamma di modelli di apprendimento addestrati per rilevare i messaggi di phishing, insieme a un insieme di algoritmi avanzati utilizzati per la protezione da attacchi di rappresentazione utente e domini diversi. Protezione anti-phishing degli strumenti di analisi consente di proteggere l'organizzazione in base a criteri che sono impostati dagli amministratori della protezione globali di Office 365.
  
Per ulteriori informazioni, vedere [impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> Protezione anti-phishing degli strumenti di analisi è disponibile solo in avanzate rischio protezione, disponibile con Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, avanzate Threat Protection può essere acquistato come componente aggiuntivo. (Come un amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni sulle opzioni di pianificazione, vedere [confrontare tutte Office 365 per piani aziendali](https://go.microsoft.com/fwlink/?linkid=844053). 
    
## <a name="how-atp-anti-phishing-works"></a>Funzionamento degli strumenti di analisi anti-phishing
<a name="Howantiphishworks"> </a>

Protezione anti-phishing degli strumenti di analisi verifica messaggi in arrivo per gli indicatori che il messaggio può essere phishing. Ogni volta che un utente è occupato da un criterio degli strumenti di analisi (gli allegati sicuri, collegamenti attendibili o anti-phishing) il messaggio in arrivo viene valutato in base al computer più modelli per l'analisi per determinare se i criteri si applicano al messaggio e l'azione appropriata per il messaggio di apprendimento eseguire, in base ai criteri configurati.
  
Degli strumenti di analisi anti-phishing consente agli amministratori globali di Office 365 o gli amministratori di sicurezza definire i criteri che forniscono una protezione contro gli attacchi di phishing che includono la rappresentazione degli utenti o i domini. (o entrambi). Gli amministratori globali di Office 365 o gli amministratori di sicurezza definiscono all'interno del criterio utente e i domini deve essere protette da attacchi di rappresentazione utente utilizzando un elenco fisso di utenti o i domini o mediante l'utilizzo di business intelligence della cassetta postale. Business intelligence della cassetta postale è una conoscenza approfondita di specifiche esigenze di posta elettronica dell'utente e i contatti personali. Degli strumenti di analisi acquisita dalla modalità di ogni singolo utente comunica con altri utenti all'interno e all'esterno dell'organizzazione e vengono creati una mappa di queste relazioni. Questa mappa consente di acquisire familiarità con ulteriori informazioni su come verificare i messaggi destro vengono identificati come rappresentazione degli strumenti di analisi.
  
Criteri anti-phishing degli strumenti di analisi può essere applicato a un insieme specifico di utenti o gruppi all'interno dell'organizzazione o a un intero dominio o a tutti i domini personalizzati. Per ulteriori informazioni, vedere [impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Come ottenere degli strumenti di analisi anti-phishing
<a name="Howtogetantiphish"> </a>

Protezione anti-phishing degli strumenti di analisi fa parte di avanzate di rischio protezione, è incluso in Office 365 Enterprise E5. Protezione avanzata di rischio inoltre può essere acquistata come componente aggiuntivo per Office 365 Enterprise E1 o E3 Enterprise di Office 365. Per ulteriori informazioni sulle opzioni di pianificazione, vedere [confrontare tutte Office 365 per piani aziendali](https://go.microsoft.com/fwlink/?linkid=844053).
  
Protezione anti-phishing degli strumenti di analisi si applica quando un criterio di protezione anti-phishing, ad esempio siano configurati un criterio di rappresentazione. Vedere [impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Come sapere se anti-phishing degli strumenti di analisi è sul posto
<a name="IsantiphishOn"> </a>

Criteri di anti-phishing degli strumenti di analisi devono essere definiti nell'ordine indicato per la protezione è attivo. Per i modelli di protezione anti-phishing apprendimento degli strumenti di analisi è attivo per un utente, l'utente deve essere parte di un allegato sicuro definito, collegamenti attendibili o dei criteri anti-phishing. Nella tabella seguente vengono descritti alcuni scenari di esempio. In ognuno di questi esempi, l'organizzazione utilizza Office 365 Enterprise E5, che include una protezione avanzata di rischio.
  
|**Scenario di esempio**|**Protezione anti-phishing degli strumenti di analisi si applica in questo caso?**|
|:-----|:-----|
|Organizzazione di PAT ha E5 Enterprise di Office 365, ma non è definita tutti i criteri per gli allegati sicuri di strumenti di analisi, degli strumenti di analisi collegamenti attendibili o degli strumenti di analisi avanzate phishing ancora.|No. Sebbene la funzionalità è disponibile, almeno un criterio degli strumenti di analisi deve essere definito nell'ordine indicato per i modelli di apprendimento degli strumenti di analisi per l'utilizzo. Per la rappresentazione un criterio di protezione anti-phishing degli strumenti di analisi deve inoltre essere sul posto.|
|Lee è un dipendente del reparto vendite presso Contoso. Organizzazione di Lee dispone di un criterio di protezione anti-phishing degli strumenti di analisi cui si applica solo ai dipendenti finance.|No. In questo caso, degli strumenti di analisi anti-phishing (modelli computer e la tutela della rappresentazione) si applicano a finance dipendenti, mentre altri dipendenti, tra cui il reparto vendite non.|
|Nel giorno precedente, un amministratore di Office 365 all'organizzazione di Jean configurare un criterio di protezione anti-phishing degli strumenti di analisi che si applica a tutti i dipendenti. In precedenza oggi Jean ricevuto un messaggio di posta elettronica che include una rappresentazione a cui il criterio.|Sì. In questo esempio Jean dispone di una licenza per la protezione avanzata di rischio e un criterio di protezione anti-phishing degli strumenti di analisi che include Jean è stato definito. In genere necessario circa 30 minuti per un nuovo criterio rendere effettive tra datacenter; Poiché un giorno trascorsa in questo caso, il criterio deve essere attivo.|
   
## <a name="related-topics"></a>Argomenti correlati
<a name="IsantiphishOn"> </a>

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Protezione anti-phishing in Office 365](anti-phishing-protection.md)
  
[Impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md)
  
[Collegamenti sicuri degli strumenti di analisi in Office 365](atp-safe-links.md)
  
[Impostare i criteri di strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)
  
[Allegati sicuri degli strumenti di analisi in Office 365](atp-safe-attachments.md)
  
[Impostare i criteri di sicurezza degli allegati degli strumenti di analisi in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)
  

