---
title: Collegamenti sicuri di Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/11/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La funzionalità collegamenti sicuri fornisce il tempo di fare clic sulla verifica dei link ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Utilizzare collegamenti sicuri per proteggere l'organizzazione da attacchi di phishing e altri.
ms.openlocfilehash: dbcedc48cbda844054e5c06a91adf3cdf30a0634
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123947"
---
# <a name="office-365-atp-safe-links"></a>Collegamenti sicuri di Office 365 ATP

## <a name="overview-of-office-365-atp-safe-links"></a>Panoramica dei collegamenti sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è destinato ai clienti aziendali. Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP Safe Links (parte di [Advanced Threat Protection](office-365-atp.md)) può aiutare a proteggere l'organizzazione fornendo la verifica del tempo di clic degli indirizzi Web (URL) nei [messaggi di posta elettronica](#how-atp-safe-links-works-with-email) e nei [documenti di Office](#how-atp-safe-links-works-with-office-documents). La protezione è definita tramite i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) impostati dal team di sicurezza di Office 365. 
  
Una volta che i criteri dei collegamenti sicuri di ATP sono sul posto, gli amministratori globali di Office 365, gli amministratori della sicurezza e i lettori di sicurezza possono [visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md). Le informazioni contenute in tali relazioni consentono al team di sicurezza di eseguire ulteriori operazioni per proteggere l'organizzazione o gli incidenti di sicurezza della ricerca.

Quando [si aggiungono nuove funzionalità a ATP](office-365-atp.md#new-features-in-office-365-atp), il team di sicurezza di Office 365 può aggiungere o modificare i criteri dei collegamenti sicuri di ATP dell'organizzazione. È inoltre possibile notare modifiche e miglioramenti, ad esempio le [pagine di avviso](atp-safe-links-warning-pages.md) appena rivedute e il rendering del collegamento nativo in Outlook.
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Funzionamento dei collegamenti sicuri di ATP con gli URL nella posta elettronica

A livello elevato, ecco come funziona la protezione dei collegamenti sicuri di ATP per gli URL nella posta elettronica (ospitati in Office 365, non in locale):
  
1. Gli utenti ricevono messaggi di posta elettronica, alcuni dei quali contengono URL.
    
2. Tutti i messaggi di posta elettronica passano attraverso Exchange Online Protection, dove vengono applicati i filtri Internet (IP) e busta, la protezione antimalware basata sulle firme, i filtri anti-spam e antivirus. 
    
3. La posta elettronica arriva nelle cassette postali degli utenti.
    
4. Un utente accede a Office 365 e passa alla posta in arrivo.
    
5. L'utente apre un messaggio di posta elettronica e fa clic su un URL nel messaggio di posta elettronica.
    
6. La caratteristica collegamenti sicuri ATP verifica immediatamente l'URL prima di aprire il sito Web. L'URL viene identificato come bloccato, dannoso o sicuro.
    
    - Se l'URL è associato a un sito Web incluso in un [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, il sito Web verrà aperto. 
    
    - Se l'URL è incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
    - Se l'URL è associato a un sito Web che è stato determinato come dannoso, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
    - Se l'URL passa a un file scaricabile e i criteri per i [collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) dell'organizzazione sono configurati per l'analisi di tali contenuti, il file scaricabile viene controllato. 
    
    - Se l'URL è determinato per la sicurezza, il sito Web verrà aperto.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Funzionamento dei collegamenti sicuri di ATP con gli URL nei documenti di Office

A livello elevato, ecco come funziona la protezione dei collegamenti sicuri di ATP per gli URL nelle applicazioni di ProPlus di Office 365 (versioni correnti di Word, Excel e PowerPoint su Windows o Mac, app di Office su dispositivi iOS o Android, Visio su Windows, OneNote online e Office Online):
  
1. Gli utenti hanno installato Office 365 ProPlus nel computer, nello smartphone o nel tablet. (Oppure, utilizzano Office Online nel browser).
    
2. Un utente apre una parola, Excel, PowerPoint o Visio e accede a Office 365 Enterprise utilizzando l'account aziendale o dell'Istituto di istruzione. Il documento contiene gli URL.
    
3. Quando l'utente fa clic su un URL del documento, il collegamento è controllato dal servizio collegamenti sicuri di ATP.
    
  - Se l'URL è associato a un sito Web incluso in un [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, l'utente viene indirizzato al sito Web. 
    
  - Se l'URL è associato a un sito Web incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
  - Se l'URL è associato a un sito Web che è stato determinato come dannoso, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
  - Se l'URL passa a un file scaricabile e i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di tali download, viene controllato il file scaricabile. 
    
  - Se l'URL è considerato sicuro, l'utente viene reindirizzato al sito Web.

## <a name="how-to-get-atp-safe-links-protection"></a>Come ottenere la protezione di collegamenti sicuri ATP

Prima di tutto, assicurarsi che l'abbonamento includa [protezione avanzata dalle minacce](office-365-atp.md). ATP è incluso nelle sottoscrizioni, ad esempio [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education a5 e così via. Se nell'organizzazione è presente un abbonamento a Office 365 che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 
  
Successivamente, verificare che i criteri dei collegamenti sicuri di ATP siano stati definiti. Per ulteriori informazioni, vedere [configurare i criteri dei collegamenti sicuri ATP di Office 365](set-up-atp-safe-links-policies.md). Le funzionalità dei collegamenti sicuri di ATP sono attive quando:
  
- I **criteri dei collegamenti sicuri di ATP sono** configurati per la posta elettronica e per i documenti di Word, Excel, PowerPoint e Visio. (Vedere [configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md)).

- Le **app client di Office 365 sono configurate per l'utilizzo dell'autenticazione moderna** (questo è per la protezione dei collegamenti sicuri di ATP nei documenti di Office). (Vedere [autenticazione moderna per Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)). 
    
- **Gli utenti hanno effettuato l'accesso a Office 365** utilizzando l'account aziendale o dell'Istituto di istruzione. (Vedere [accedere a Office o office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)).
    
- **La posta elettronica dell'organizzazione passa attraverso Exchange Online Protection**.  

Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente:

|Ruolo  |Dove/come assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
|Gestione dell'organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Come assicurarsi che la protezione di collegamenti sicuri di ATP sia sul posto

In qualità di amministratore globale o amministratore della sicurezza, assicurarsi di esaminare i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md). I criteri per i collegamenti sicuri di ATP determinano se la protezione si applica ai collegamenti ipertestuali solo nei messaggi di posta elettronica o agli URL nei documenti di Office.

Dopo che i criteri per i collegamenti sicuri di ATP sono sul posto, il team di sicurezza dell'organizzazione può vedere come la protezione dei collegamenti sicuri di ATP è in funzione per l'organizzazione è [visualizzando i report per Advanced Threat Protection](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Scenari di esempio
  
Nella tabella seguente vengono descritti alcuni scenari di esempio in cui la protezione dei collegamenti sicuri di ATP potrebbe o meno essere sul posto. In tutti questi casi, si presuppone che l'organizzazione disponga di Office 365 Enterprise E5.
  
|**Scenario di esempio**|**La protezione di collegamenti sicuri ATP è applicabile in questo caso?**|
|:-----|:-----|
|Jean è un membro di un gruppo che dispone di criteri dei collegamenti sicuri di ATP che coprono gli URL nella posta elettronica e nei documenti di Office. Jean apre una presentazione di PowerPoint inviata da un utente e quindi fa clic su un URL nella presentazione.  <br/> |Sì. I criteri per i collegamenti sicuri di ATP definiti si applicano al gruppo di Jean, alla posta elettronica di Jean e ai documenti Word, Excel, PowerPoint o Visio che Jean apre, purché Jean sia connesso e utilizzi Office 365 ProPlus nei dispositivi Windows, iOS o Android.  <br/> |
|Nell'organizzazione di Chris, nessun amministratore globale o di sicurezza ha ancora definito criteri di collegamenti sicuri ATP. Chris riceve un messaggio di posta elettronica contenente un URL di un sito Web malintenzionato. Chris non è a conoscenza che l'URL è dannoso e fa clic sul collegamento.  <br/> |No. Il criterio predefinito che include gli URL per tutti gli utenti dell'organizzazione deve essere definito in modo che la protezione sia sul posto.  <br/> |
|Nell'organizzazione di Pat, nessun amministratore globale o di sicurezza ha ancora definito o modificato i criteri per i collegamenti sicuri ATP. Pat apre un documento di Word e fa clic su un URL nel file.  <br/> |No. è necessario definire un criterio che includa i documenti di Office in modo che la protezione sia sul posto. Vedere [configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md).<br/> |
|L'organizzazione di Lee ha un criterio per i collegamenti sicuri `http://tailspintoys.com` di ATP che è elencato come sito Web bloccato. Lee riceve un messaggio di `http://tailspintoys.com/aboutus/trythispage`posta elettronica che contiene un URL. Lee fa clic sull'URL.<br/> |Dipende dal fatto che l'intero sito e tutte le relative pagine secondarie siano inclusi nell'elenco degli URL bloccati. Vedere [configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).<br/> |
|Jamie, collega di Jean, invia un messaggio di posta elettronica a Jean, non sapendo che l'indirizzo di posta elettronica contiene un URL dannoso.  <br/> |Dipende dal fatto che i criteri per i collegamenti sicuri di ATP sono definiti per la posta elettronica inviata all'interno dell'organizzazione. Vedere [configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md).<br/> |


  

