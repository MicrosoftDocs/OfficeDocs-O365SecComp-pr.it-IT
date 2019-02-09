---
title: Le funzionalità di anti-phishing ATP in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
description: Anti-phishing degli strumenti di analisi fa parte di protezione di Office 365 avanzate rischio. Anti-phishing degli strumenti di analisi si applica un insieme di modelli di apprendimento automatica insieme ad algoritmi di rilevamento di rappresentazione per i messaggi in arrivo per fornire la protezione per gli attacchi di phishing merce e spear. Tutti i messaggi sono soggetti a un'ampia gamma di modelli di apprendimento addestrati per rilevare i messaggi di phishing, insieme a un insieme di algoritmi avanzati utilizzati per la protezione da attacchi di rappresentazione utente e domini diversi.
ms.openlocfilehash: c3e44a313bf9c823fbfda138fc5a10294993d509
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792271"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Le funzionalità di anti-phishing ATP in Office 365

Anti-phishing degli strumenti di analisi fa parte di [Protezione di Office 365 avanzate rischio](office-365-atp.md). Anti-phishing degli strumenti di analisi si applica un insieme di modelli di apprendimento automatica insieme ad algoritmi di rilevamento di rappresentazione per i messaggi in arrivo per fornire la protezione per gli attacchi di phishing merce e spear. Tutti i messaggi sono soggetti a un'ampia gamma di modelli di apprendimento addestrati per rilevare i messaggi di phishing, insieme a un insieme di algoritmi avanzati utilizzati per la protezione da attacchi di rappresentazione utente e domini diversi. Protezione anti-phishing degli strumenti di analisi consente di proteggere l'organizzazione in base a criteri che sono impostati dagli amministratori della protezione globali di Office 365.
  
Per ulteriori informazioni, vedere [impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> Protezione anti-phishing degli strumenti di analisi è disponibile solo in avanzate Threat Protection, incluso nel sottoscrizioni, ad esempio [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), E5 Enterprise di Office 365, Office 365 Education A5 e così via. Se l'organizzazione dispone di una sottoscrizione a Office 365 che non include degli strumenti di analisi di Office 365, è possibile acquistare potenzialmente degli strumenti di analisi come componente aggiuntivo. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Funzionamento degli strumenti di analisi anti-phishing

Protezione anti-phishing degli strumenti di analisi verifica messaggi in arrivo per gli indicatori che il messaggio può essere phishing. Ogni volta che un utente è occupato da un criterio degli strumenti di analisi (gli allegati sicuri, collegamenti attendibili o anti-phishing) il messaggio in arrivo viene valutato in base al computer più modelli per l'analisi per determinare se i criteri si applicano al messaggio e l'azione appropriata per il messaggio di apprendimento eseguire, in base ai criteri configurati.
  
Degli strumenti di analisi anti-phishing consente agli amministratori globali di Office 365 o gli amministratori di sicurezza definire i criteri che forniscono una protezione contro gli attacchi di phishing che includono la rappresentazione degli utenti o i domini. (o entrambi). Gli amministratori globali di Office 365 o gli amministratori di sicurezza definiscono all'interno del criterio utente e i domini deve essere protette da attacchi di rappresentazione utente utilizzando un elenco fisso di utenti o i domini o mediante l'utilizzo di business intelligence della cassetta postale. Business intelligence della cassetta postale è una conoscenza approfondita di specifiche esigenze di posta elettronica dell'utente e i contatti personali. Degli strumenti di analisi acquisita dalla modalità di ogni singolo utente comunica con altri utenti all'interno e all'esterno dell'organizzazione e vengono creati una mappa di queste relazioni. Questa mappa consente di acquisire familiarità con ulteriori informazioni su come verificare i messaggi destro vengono identificati come rappresentazione degli strumenti di analisi.
  
Criteri anti-phishing degli strumenti di analisi può essere applicato a un insieme specifico di utenti o gruppi all'interno dell'organizzazione o a un intero dominio o a tutti i domini personalizzati. Per ulteriori informazioni, vedere [impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Come ottenere degli strumenti di analisi anti-phishing

Funzionalità ATP Anti-Phishing fanno parte della [Protezione da minacce avanzate](office-365-atp.md); protezione anti-phishing degli strumenti di analisi, tuttavia, si applica quando vengono definiti i criteri anti-phishing. (Un esempio è un criterio di rappresentazione). Vedere [impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Come sapere se anti-phishing degli strumenti di analisi è sul posto

Criteri di anti-phishing degli strumenti di analisi devono essere definiti nell'ordine indicato per applicare la protezione. Verificare innanzitutto per verificare la protezione sia sul posto.

Inoltre, rapporti sono disponibili per mostrare come il servizio funzioni per l'organizzazione. Per ulteriori informazioni, vedere [visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md).

Per strumenti di analisi anti-phishing di apprendimento modelli per essere attiva per un determinato utente, l'utente deve essere parte di un criterio definito [Allegati sicuri degli strumenti di analisi](atp-safe-attachments.md), [Degli strumenti di analisi collegamenti attendibili](atp-safe-links.md)o ATP Anti-Phishing. 

Nella tabella seguente vengono descritti alcuni scenari di esempio. In ognuno di questi esempi, l'organizzazione utilizza Office 365 Enterprise E5, che include una protezione avanzata di rischio.
  
|**Scenario di esempio**|**Protezione anti-phishing degli strumenti di analisi si applica in questo caso?**|
|:-----|:-----|
|Organizzazione di PAT ha E5 Enterprise di Office 365, ma non è definita tutti i criteri per gli allegati sicuri di strumenti di analisi, degli strumenti di analisi collegamenti attendibili o degli strumenti di analisi avanzate phishing ancora.|No. Sebbene la funzionalità è disponibile, almeno un criterio degli strumenti di analisi deve essere definito nell'ordine indicato per i modelli di apprendimento degli strumenti di analisi per l'utilizzo. Per la rappresentazione un criterio di protezione anti-phishing degli strumenti di analisi deve inoltre essere sul posto.|
|Lee è un dipendente del reparto vendite presso Contoso. Organizzazione di Lee dispone di un criterio di protezione anti-phishing degli strumenti di analisi cui si applica solo ai dipendenti finance.|No. In questo caso, degli strumenti di analisi anti-phishing (modelli computer e la tutela della rappresentazione) si applicano a finance dipendenti, mentre altri dipendenti, tra cui il reparto vendite non.|
|Nel giorno precedente, un amministratore di Office 365 all'organizzazione di Jean configurare un criterio di protezione anti-phishing degli strumenti di analisi che si applica a tutti i dipendenti. In precedenza oggi Jean ricevuto un messaggio di posta elettronica che include una rappresentazione a cui il criterio.|Sì. In questo esempio Jean dispone di una licenza per la protezione avanzata di rischio e un criterio di protezione anti-phishing degli strumenti di analisi che include Jean è stato definito. In genere necessario circa 30 minuti per un nuovo criterio rendere effettive tra datacenter; Poiché un giorno trascorsa in questo caso, il criterio deve essere attivo.|

## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Protezione anti-phishing in Office 365](anti-phishing-protection.md)
  
[Impostazione dei criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md)
  
[Collegamenti sicuri degli strumenti di analisi in Office 365](atp-safe-links.md)
  
[Impostare i criteri di strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)
  
[Allegati sicuri degli strumenti di analisi in Office 365](atp-safe-attachments.md)
  
[Impostare i criteri di sicurezza degli allegati degli strumenti di analisi in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)
