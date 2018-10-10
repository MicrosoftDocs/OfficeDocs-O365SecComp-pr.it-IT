---
title: Collegamenti sicuri di Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
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
ms.openlocfilehash: 75703cbe6b6a5a5d102570288bb20e6814d095fc
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454373"
---
# <a name="office-365-atp-safe-links"></a>Collegamenti sicuri di Office 365 ATP

## <a name="overview-of-office-365-atp-safe-links"></a>Panoramica di Office 365 Safe degli strumenti di analisi collegamenti

Collegamenti sicuro degli strumenti di analisi Office 365 (degli strumenti di analisi collegamenti sicuro) (insieme a [Office 365 degli strumenti di analisi provvisoria allegati](atp-safe-attachments.md)) è un set di caratteristiche di sicurezza distribuito come parte di [Protezione di Office 365 avanzate minaccia](office-365-atp.md) per le organizzazioni aziendali. Collegamenti sicuro degli strumenti di analisi consentono di proteggere l'organizzazione fornendo il momento del clic verifica degli indirizzi web (URL) in [Office documenti](#how-atp-safe-links-works-with-office-documents)e [messaggi di posta elettronica](#how-atp-safe-links-works-with-email) . Protezione viene definita tramite i [criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md) impostate dal team di protezione di Office 365. 
  
Dopo aver installato i criteri degli strumenti di analisi collegamenti sicuro sul posto, gli amministratori globali di Office 365, security administrators e lettori sicurezza possono [visualizzare i report per la protezione avanzata di rischio](view-reports-for-atp.md). Le informazioni contenute in questi rapporti consentono al team di protezione eseguire ulteriori passaggi per proteggere l'organizzazione o problemi di protezione di ricerca.
         
### <a name="how-atp-safe-links-works-with-urls-in-email"></a>Funzionamento degli strumenti di analisi collegamenti sicuro con URL nel messaggio di posta elettronica

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
    
### <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Funzionamento degli strumenti di analisi collegamenti provvisoria gli URL nei documenti di Office

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

Caratteristiche degli strumenti di analisi collegamenti sicuri fanno parte di [Protezione da minacce avanzate](office-365-atp.md), incluso in Office 365 Enterprise E5, Microsoft Business 365 e Microsoft 365 Enterprise. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, avanzate Threat Protection può essere acquistato come componente aggiuntivo. Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).
  
Le caratteristiche degli strumenti di analisi collegamenti attendibili sono attivi quando:
  
- **Vengono impostati i criteri degli strumenti di analisi collegamenti sicuri** per la posta elettronica e per i documenti di Word, Excel, PowerPoint e Visio. Vedere [impostazione dei criteri di strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).

- **Applicazioni client di office 365 sono configurate per utilizzare l'autenticazione moderno**. (Vedere [moderno Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)). 
    
- **Gli utenti hanno effettuato l'accesso a Office 365** utilizzando il proprio account di lavoro o della scuola. Vedere [accesso a Office o Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).
    
- **Che messaggio di posta elettronica dell'organizzazione è ospitata in Office 365**, non in un server locale. 
    
### <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Come rendere protezione degli strumenti di analisi collegamenti provvisoria che è sul posto

Un modo efficace per vedere modalità di utilizzo di protezione degli strumenti di analisi collegamenti sicuri per l'organizzazione è visualizzando i [report per la protezione avanzata di rischio](view-reports-for-atp.md). Inoltre, un amministratore globale o un amministratore di protezione, assicurarsi di esaminare i [criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md). Collegamenti sicuro degli strumenti di analisi criteri determinano se protezione si applica a collegamenti ipertestuali nei messaggi di posta elettronica solo o agli URL in anche i documenti di Office.

### <a name="example-scenarios-where-atp-safe-links-protection-might-or-might-not-be-in-place"></a>Scenari di esempio cui protezione degli strumenti di analisi collegamenti sicuro potrebbe o potrebbe non essere sul posto
  
Nella tabella seguente vengono descritti alcuni scenari di esempio in protezione degli strumenti di analisi collegamenti attendibili potrebbero o potrebbe non essere presenti. (In tutti i casi, si presuppone che l'organizzazione dispone di Office 365 Enterprise E5.)
  
|**Scenario di esempio**|**Protezione degli strumenti di analisi collegamenti sicuro si applica in questo caso?**|
|:-----|:-----|
|Jean è un membro di un gruppo con i criteri degli strumenti di analisi collegamenti provvisoria gli URL relativi alla posta elettronica e documenti di Office. Jean apre una presentazione di PowerPoint da un utente inviati e quindi fa clic su un URL nella presentazione.  <br/> |Sì. I criteri degli strumenti di analisi collegamenti attendibili definiti si applicano a di Jean gruppo, di Jean messaggio di posta elettronica e documenti di Word, Excel, PowerPoint o Visio Jean visualizzata, purché Jean ha eseguito l'accesso e l'utilizzo Office 365 ProPlus in Windows, iOS o dispositivi Android.  <br/> |
|Nell'organizzazione, non globale o sicurezza Chris gli amministratori hanno definito ancora tutti i criteri di collegamenti sicuro degli strumenti di analisi. Chris riceve un messaggio di posta elettronica contenente un URL di un sito Web dannoso. Chris in grado di riconoscere l'URL è dannoso e fa clic sul collegamento.  <br/> |No. Il criterio predefinito che vengono trattati gli URL per tutti gli utenti dell'organizzazione deve essere definito nell'ordine indicato per la protezione in locale.  <br/> |
|In mia organizzazione non globale o security administrators definito o modificati tutti i criteri degli strumenti di analisi collegamenti sicuri ancora. PAT viene aperto un documento di Word e fa clic su un URL nel file.  <br/> |Criteri A No. che includono i documenti di Office devono essere definito nell'ordine indicato per la protezione in locale. Vedere [impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).<br/> |
|Organizzazione di Lee dispone di un criterio degli strumenti di analisi collegamenti sicuro con `http://tailspintoys.com` elencato come un sito Web bloccato. Lee riceve un messaggio di posta elettronica contenente un URL di `http://tailspintoys.com/aboutus/trythispage`. Lee fa clic sull'URL.<br/> |Dipende dal fatto l'intero sito tutte quelle secondarie sono inclusi nell'elenco dei bloccati gli URL. Vedere [impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-blocked-urls-list-wtih-atp.md).<br/> |
|Chiara, importazione suggerimenti colleghi di Jean, invia un messaggio di posta elettronica a Jean, senza sapere che il messaggio di posta elettronica contiene un URL dannoso.  <br/> |Dipende dal fatto definiti criteri degli strumenti di analisi collegamenti sicuri per la posta elettronica inviato all'interno dell'organizzazione. Vedere [impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).<br/> |

## <a name="new-features-are-continually-being-added-to-atp-safe-links"></a>Nuove funzionalità vengono aggiunti continuamente ai collegamenti sicuro degli strumenti di analisi

Stiamo continuando ad aggiungere nuove caratteristiche degli strumenti di analisi collegamenti sicuri. In alcuni casi una nuova funzionalità chiama per i criteri di collegamenti sicuro degli strumenti di analisi deve essere esaminato e aggiornato. Di seguito sono riportati esempi di diversi:
  
- A partire da ritardo ottobre 2017, protezione degli strumenti di analisi collegamenti sicuro viene estesa per applicare agli URL nel messaggio di posta elettronica, nonché gli URL nei documenti di Office 365 ProPlus, ad esempio Word, Excel, PowerPoint e Visio in Windows, nonché Office apps iOS e dispositivi Android. (Verificare che si sta utilizzando [l'Autenticazione moderno per Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)).
    
- A partire da marzo 2018 protezione degli strumenti di analisi collegamenti sicuro viene estesa per applicare alla posta elettronica inviato tra utenti all'interno dell'organizzazione. (Assicurarsi di [esaminare e modificare i criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md).)
 
- A partire dalla seconda parte del 2018 protezione degli strumenti di analisi collegamenti sicuro viene estesa per applicare agli URL in Office Online (Online di Word, Excel Online, in linea di PowerPoint e OneNote Online) e Office 365 ProPlus su Mac. (Assicurarsi di [esaminare e modificare i criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md).)

- Inizio in settembre 2018, [pagine di avviso degli strumenti di analisi di Office 365](atp-safe-links-warning-pages.md) caratteristica una nuova combinazione di colori, ulteriori dettagli e la possibilità di continuare a un sito nonostante assegnate gli avvisi e suggerimenti. 
 
- A partire da ottobre 2018 e distribuzione sui prossimi mesi, quando gli utenti utilizzano Outlook Web Application (OWA) o Outlook, degli strumenti di analisi collegamenti sicuro viene eseguito il rendering degli URL originali, non riscritto URL. (Viene chiamato questo visibilità collegamento nativa).

   
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)
  
[Allegati degli strumenti di analisi sicuro in Office 365](atp-safe-attachments.md)
  
[Funzionalità di anti-phishing ATP in Office 365](atp-anti-phishing.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)
  

