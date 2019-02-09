---
title: Collegamenti sicuri di Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/05/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La caratteristica di collegamenti sicuro offre verifica momento del clic dei collegamenti ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Utilizzare i collegamenti sicuri per proteggere l'organizzazione di phishing e altri attacchi.
ms.openlocfilehash: 8c63de9e62e33dbca6dde5a5bb45a7f7875ab71f
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792241"
---
# <a name="office-365-atp-safe-links"></a>Collegamenti sicuri di Office 365 ATP

## <a name="overview-of-office-365-atp-safe-links"></a>Panoramica di Office 365 Safe degli strumenti di analisi collegamenti

> [!IMPORTANT]
> In questo articolo è destinato ai clienti aziendali. Se si è un utente principale per informazioni su collegamenti sicuro in Outlook, vedere [sicurezza avanzata Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Collegamenti sicuro degli strumenti di analisi di Office 365 (parte di [Protezione avanzata di rischio](office-365-atp.md)) consentono di proteggere l'organizzazione fornendo il momento del clic verifica degli indirizzi web (URL) in [Office documenti](#how-atp-safe-links-works-with-office-documents)e [messaggi di posta elettronica](#how-atp-safe-links-works-with-email) . Protezione viene definita tramite i [criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md) impostate dal team di protezione di Office 365. 
  
Dopo aver installato i criteri degli strumenti di analisi collegamenti sicuro sul posto, gli amministratori globali di Office 365, security administrators e lettori sicurezza possono [visualizzare i report per la protezione avanzata di rischio](view-reports-for-atp.md). Le informazioni contenute in questi rapporti consentono al team di protezione eseguire ulteriori passaggi per proteggere l'organizzazione o problemi di protezione di ricerca.

Come [vengono aggiunte nuove funzionalità per strumenti di analisi](office-365-atp.md#new-features-are-continually-being-added-to-atp), il team di protezione di Office 365 aggiungere o modificare i criteri dell'organizzazione degli strumenti di analisi collegamenti sicuri. Inoltre, è possibile notare miglioramenti, ad esempio il nostro appena rivisto [pagine di avviso](atp-safe-links-warning-pages.md) e collegamento nativo per il rendering in Outlook e le modifiche.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Funzionamento degli strumenti di analisi collegamenti sicuro con URL nel messaggio di posta elettronica

In dettaglio, ecco collegamenti sicuro degli strumenti di analisi del funzionamento della protezione per gli URL nella posta elettronica (ospitata in Office 365 non locale):
  
1. Gli utenti ricevono messaggi di posta elettronica, alcuni dei quali contengono URL.
    
2. Viene inoltrata tutta la posta elettronica tramite Exchange Online Protection, dove IP (internet protocol) e busta i filtri, protezione da malware basata su firma, protezione da posta indesiderata e anti-malware filtri vengono applicati. 
    
3. I messaggi arrivano nella posta in arrivo di utenti.
    
4. Un utente accede a Office 365 e passa alla posta in arrivo di posta elettronica.
    
5. L'utente fa clic su un URL nel messaggio di posta elettronica viene aperto un messaggio di posta elettronica.
    
6. La funzionalità degli strumenti di analisi collegamenti sicuri immediatamente controllerà l'URL prima di aprire il sito Web. L'URL viene identificato come bloccato, dannoso o sicuri.
    
    - Se l'URL di un sito Web incluso in un [elenco degli URL "non di riscrittura" personalizzato](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, viene aperto il sito Web. 
    
    - Se l'URL di un sito Web inclusa in dell'organizzazione [personalizzato bloccati gli URL](set-up-a-custom-blocked-urls-list-wtih-atp.md), verrà visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
    - Se l'URL di un sito Web che è stato determinato che dannoso, verrà visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
    - Se l'URL viene inserito in un file scaricabile e dell'organizzazione [degli strumenti di analisi collegamenti sicuro politiche](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di questo tipo di contenuto, viene controllato il file disponibile. 
    
    - Se l'URL è determinata da sicuro, viene aperto il sito Web.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Funzionamento degli strumenti di analisi collegamenti provvisoria gli URL nei documenti di Office

In dettaglio, ecco funzionamento della protezione degli strumenti di analisi collegamenti sicuri per gli URL nelle applicazioni di Office 365 ProPlus (versioni correnti di Word, Excel e PowerPoint in Windows o Mac, applicazioni di Office su iOS o dispositivi Android, Visio su Windows, OneNote Online e Office Online):
  
1. Utenti sono installati Office 365 ProPlus nel proprio computer, smartphone o Tablet PC. In alternativa, utilizzano Office Online nel browser.
    
2. Un utente accede a Office 365 Enterprise utilizzando il proprio account di lavoro o della scuola viene aperto un Word, Excel, PowerPoint o Visio. Il documento contiene gli URL.
    
3. Quando l'utente fa clic su un URL nel documento, il collegamento viene controllato dal servizio collegamenti sicuro degli strumenti di analisi.
    
  - Se l'URL di un sito Web incluso in un [elenco degli URL "non di riscrittura" personalizzato](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, l'utente passa al sito Web. 
    
  - Se l'URL di un sito Web inclusa in dell'organizzazione [personalizzato bloccati gli URL](set-up-a-custom-blocked-urls-list-wtih-atp.md), l'utente passa a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
  - Se l'URL di un sito Web che è stato determinato che dannoso, l'utente passa a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
  - Se l'URL viene inserito in un file scaricabile e i [criteri degli strumenti di analisi collegamenti attendibili](set-up-atp-safe-links-policies.md) sono configurati per l'analisi tali download, viene controllato il file disponibile. 
    
  - Se l'URL è considerato sicuro, l'utente viene indirizzato al sito Web.

## <a name="how-to-get-atp-safe-links-protection"></a>Come ottenere protezione degli strumenti di analisi collegamenti sicuri

Per prima cosa, verificare che la sottoscrizione include [Avanzate Threat Protection](office-365-atp.md). Degli strumenti di analisi è incluso in sottoscrizioni, ad esempio [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), E5 Enterprise di Office 365, Office 365 Education A5 e così via. Se l'organizzazione dispone di una sottoscrizione a Office 365 che non include degli strumenti di analisi di Office 365, è possibile acquistare potenzialmente degli strumenti di analisi come componente aggiuntivo. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 
  
Quindi, verificare che i criteri degli strumenti di analisi collegamenti attendibili sono definiti. Vedere [impostazione dei criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](set-up-atp-safe-links-policies.md). Caratteristiche degli strumenti di analisi collegamenti sicuri siano attive quando:
  
- **Vengono impostati i criteri degli strumenti di analisi collegamenti sicuri** per la posta elettronica e per i documenti di Word, Excel, PowerPoint e Visio. Vedere [impostazione dei criteri di strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).

- **Applicazioni client di Office 365 sono configurate per utilizzare l'autenticazione moderno** (si tratta per la protezione degli strumenti di analisi provvisoria collegamenti nei documenti di Office). (Vedere [moderno Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)). 
    
- **Gli utenti hanno effettuato l'accesso a Office 365** utilizzando il proprio account di lavoro o della scuola. Vedere [accesso a Office o Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).
    
- **Messaggio di posta elettronica dell'organizzazione è ospitata in Office 365**. 

Per definire o modificare i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito:

|Ruolo  |Modalità assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organization Management |Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Come rendere protezione degli strumenti di analisi collegamenti provvisoria che è sul posto

Un amministratore globale o un amministratore di protezione, assicurarsi di esaminare i [criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md). Collegamenti sicuro degli strumenti di analisi criteri determinano se protezione si applica a collegamenti ipertestuali nei messaggi di posta elettronica solo o agli URL in anche i documenti di Office.

Dopo aver criteri degli strumenti di analisi collegamenti sicuro, team di protezione dell'organizzazione possono visualizzare vedere come funziona protezione degli strumenti di analisi collegamenti sicuri per l'organizzazione è dalla [visualizzazione di report per la protezione avanzata di rischio](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Scenari di esempio
  
Nella tabella seguente vengono descritti alcuni scenari di esempio in protezione degli strumenti di analisi collegamenti attendibili potrebbero o potrebbe non essere presenti. (In tutti i casi, si presuppone che l'organizzazione dispone di Office 365 Enterprise E5.)
  
|**Scenario di esempio**|**Protezione degli strumenti di analisi collegamenti sicuro si applica in questo caso?**|
|:-----|:-----|
|Jean è un membro di un gruppo con i criteri degli strumenti di analisi collegamenti provvisoria gli URL relativi alla posta elettronica e documenti di Office. Jean apre una presentazione di PowerPoint da un utente inviati e quindi fa clic su un URL nella presentazione.  <br/> |Sì. I criteri degli strumenti di analisi collegamenti attendibili definiti si applicano a di Jean gruppo, di Jean messaggio di posta elettronica e documenti di Word, Excel, PowerPoint o Visio Jean visualizzata, purché Jean ha eseguito l'accesso e l'utilizzo Office 365 ProPlus in Windows, iOS o dispositivi Android.  <br/> |
|Nell'organizzazione, non globale o sicurezza Chris gli amministratori hanno definito ancora tutti i criteri di collegamenti sicuro degli strumenti di analisi. Chris riceve un messaggio di posta elettronica contenente un URL di un sito Web dannoso. Chris in grado di riconoscere l'URL è dannoso e fa clic sul collegamento.  <br/> |No. Il criterio predefinito che vengono trattati gli URL per tutti gli utenti dell'organizzazione deve essere definito nell'ordine indicato per la protezione in locale.  <br/> |
|In mia organizzazione non globale o security administrators definito o modificati tutti i criteri degli strumenti di analisi collegamenti sicuri ancora. PAT viene aperto un documento di Word e fa clic su un URL nel file.  <br/> |Criteri A No. che includono i documenti di Office devono essere definito nell'ordine indicato per la protezione in locale. Vedere [impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).<br/> |
|Organizzazione di Lee dispone di un criterio degli strumenti di analisi collegamenti sicuro con `http://tailspintoys.com` elencato come un sito Web bloccato. Lee riceve un messaggio di posta elettronica contenente un URL di `http://tailspintoys.com/aboutus/trythispage`. Lee fa clic sull'URL.<br/> |Dipende dal fatto l'intero sito tutte quelle secondarie sono inclusi nell'elenco dei bloccati gli URL. Vedere [impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-blocked-urls-list-wtih-atp.md).<br/> |
|Chiara, importazione suggerimenti colleghi di Jean, invia un messaggio di posta elettronica a Jean, senza sapere che il messaggio di posta elettronica contiene un URL dannoso.  <br/> |Dipende dal fatto definiti criteri degli strumenti di analisi collegamenti sicuri per la posta elettronica inviato all'interno dell'organizzazione. Vedere [impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).<br/> |


  

