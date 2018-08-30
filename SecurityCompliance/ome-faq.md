---
title: Domande frequenti sulla crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/23/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Ottenere informazioni su come utilizzare le nuove funzionalità di protezione dei messaggi in Office 365? Verificare di una risposta di seguito.
ms.openlocfilehash: d435642d8ea98d37a58b28b55c9c1e68c746600c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559251"
---
# <a name="office-365-message-encryption-faq"></a>Domande frequenti sulla crittografia dei messaggi di Office 365

Ottenere informazioni su come utilizzare le nuove funzionalità di protezione dei messaggi in Office 365? Verificare di una risposta di seguito. Inoltre, esaminare [domande frequenti sulla protezione dei dati in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) per le risposte alle domande relative al servizio di protezione dei dati, Azure Rights Management in Azure Information Protection. 
  
## <a name="what-is-office-365-message-encryption-ome"></a>Che cos'è Office 365 messaggio crittografia dei?

OME combina le funzionalità di gestione dei diritti e la crittografia di posta elettronica. Funzionalità di gestione dei diritti sono tecnologia per la protezione delle informazioni di Azure.
  
## <a name="who-can-use-ome"></a>Chi può utilizzare OME?

È possibile utilizzare le nuove funzionalità per OME nelle condizioni seguenti:
  
- Se mai stata configurata OME o IRM per Exchange Online in Office 365.
    
- Se è stata configurata OME e IRM, è possibile utilizzare la procedura seguente se si utilizza il servizio di Azure Rights Management dalla protezione delle informazioni di Azure.
    
- Se si utilizza Exchange Online con il servizio Active Directory Rights Management (AD RMS), sarà possibile abilitare queste nuove funzionalità immediatamente. In realtà, è necessario [eseguire la migrazione di AD RMS per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) prima. Una volta completata la migrazione, è possibile impostare correttamente OME. 
    
    Se si sceglie di continuare a utilizzare locale AD RMS con Exchange Online anziché la migrazione per la protezione delle informazioni di Azure, non sarà in grado di utilizzare queste nuove funzionalità.
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Le sottoscrizioni è necessario utilizzare le nuove funzionalità OME?

Per utilizzare le nuove funzionalità OME, è necessario uno dei seguenti piani:
  
- Office 365 Message Encryption è disponibile come parte di Office 365 E3 ed E5, E3 Microsoft ed E5, Office 365 A1, A3 e A5 e Office 365 G3 e G5. I clienti non sono necessario disporre di una licenza per ricevere le nuove funzionalità di protezione con tecnologia per la protezione delle informazioni di Azure. 
    
- È inoltre possibile aggiungere Azure Information Protection piano 1 agli elementi seguenti piani a ricevere le nuove funzionalità di Office 365 Message Encryption: Exchange Online piano 1, Exchange Online piano 2, Office 365 F1, Essentials Business di Office 365, Office 365 Business Premium o Office 365 Enterprise E1.
    
- Ogni utente beneficiano di Office 365 Message Encryption deve disporre della licenza per da coprire con la caratteristica.
    
- Per un elenco completo vedere le [descrizioni dei servizi di Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) per Office 365 Message Encryption. 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>È possibile utilizzare Exchange Online con portare il proprio codice (BYOK) Azure protezione delle informazioni?

Sì! Si consiglia di eseguire la procedura per configurare BYOK prima di impostare OME.
  
Per ulteriori informazioni su BYOK, vedere [pianificazione e l'implementazione la chiave del tenant la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>OME e BYOK con Azure Information Protection modificare approccio di Microsoft per le richieste di dati di terze parti, ad esempio citazioni?

No. OME e l'opzione per offrire e controllare il proprio chiavi di crittografia, viene chiamate BYOK, da Azure Information Protection non progettate per rispondere a citazioni applicazione della legge. OME con BYOK per la protezione delle informazioni di Azure, è stato progettato per i clienti di corsi di conformità. Microsoft ha molto prendere in seria le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, è sempre sostenere la privacy dei dati dei clienti. Nel caso in cui è possibile ottenere un mandato di comparizione, sempre eseguito un tentativo di reindirizzare la terza parte per il cliente per ottenere le informazioni. (Leggere il blog Brad Smith: [dati relativi ai clienti Protecting da government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). È periodicamente pubblicare informazioni dettagliate della richiesta che viene visualizzato. Per ulteriori informazioni sulle richieste di dati di terze parti, vedere [procedura: rispondere alle richieste di applicazione della legge per accedere ai dati dei clienti e government](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) in Microsoft Trust Center. Vedere anche "Divulgazione di dati dei clienti" in [Termini di servizi in linea (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>Relazione di questa funzionalità e caratteristiche di Information Rights Management (IRM) e Office 365 messaggio crittografia dei legacy

Le nuove funzionalità per la crittografia dei messaggi di Office 365 sono evoluzione delle IRM esistente e le soluzioni OME legacy. Nella tabella seguente sono disponibili ulteriori dettagli.
  
**Confronto tra OME legacy, IRM e le nuove funzionalità OME**

|**Funzionalità**|**Versioni precedenti di OME**|**IRM**|**Nuove funzionalità OME**|
|:-----|:-----|:-----|:-----|
|**Messaggio di posta elettronica crittografato**|Solo tramite le regole di flusso della posta di Exchange|Per l'utente finale ha avviato da Outlook per PC, Outlook per Mac o Outlook sul web. o tramite Exchange regole del flusso di posta|Per l'utente finale ha avviato da Outlook per PC, Outlook per Mac o Outlook sul web. o tramite le regole di flusso di posta elettronica|
|**Gestione dei diritti**|-|Tale opzione non inoltrare e i modelli personalizzati|Non opzione non inoltrare, opzione solo crittografare, predefinito e i modelli personalizzati|
|**Tipo di destinatario supportato**|Solo i destinatari esterni|Solo i destinatari interni|Destinatari interni ed esterni|
|**Esperienza per destinatario**|I destinatari esterni ricevuto un messaggio HTML che vengono scaricati e aprire in un browser o scaricato app per dispositivi mobili.|I destinatari interni ricevuta solo posta elettronica crittografati in Outlook per PC, Outlook per Mac e Outlook sul web.|I destinatari interni ed esterni ricevano della posta elettronica in Outlook per PC, Outlook per Mac, Outlook sul web, Outlook per Android e Outlook per iOS o tramite un portale web, indipendentemente dal fatto che siano o meno nella stessa organizzazione Office 365 o in qualsiasi Office 365 organizzazione. Il portale OME non richiede alcun download.|
|**Inserire il supporto del proprio chiave**|Non disponibile|Non disponibile| BYOK supportati|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Abilitazione di nuove funzionalità OME per l'organizzazione

Vedere [impostare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md).
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>Diventerà la versione precedente di OME obsoleto?

È comunque possibile utilizzare la versione precedente di OME, diventerà obsoleto non adesso. Tuttavia, invitiamo altamente alle organizzazioni di utilizzare la soluzione OME nuova e migliorata. I clienti che non è già stato distribuito OME non possono impostare una nuova distribuzione della versione precedente di OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Organizzazione viene utilizzato Active Directory Rights Management, è possibile utilizzare tale funzionalità?

No. Se si utilizza Exchange Online con il servizio Active Directory Rights Management (AD RMS), sarà possibile abilitare queste nuove funzionalità immediatamente. In realtà, è necessario [eseguire la migrazione di AD RMS per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) prima. 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Organizzazione dispone di una distribuzione ibrida di Exchange. È possibile utilizzare questa caratteristica?

Locale gli utenti possono inviare messaggi crittografati tramite Exchange Online regole del flusso di posta elettronica. Per ottenere questo risultato, è necessario instradare la posta elettronica tramite Exchange Online.
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>I client di posta elettronica da utilizzare per creare un messaggio crittografato OME Quali applicazioni sono supportate per l'invio di messaggi protetti?

È possibile creare messaggi protetti da 2016 Outlook e Outlook 2013 per PC e Mac e da Outlook sul web.
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>I client di posta elettronica sono supportate per leggere e rispondere ai messaggi di posta elettronica protette?

È possibile leggerli e rispondere da Outlook per PC e Mac (2013 e 2016), Outlook sul web e Outlook mobile (Android e iOS) in caso di un utente di Office 365. È inoltre possibile utilizzare i client di posta elettronica nativo iOS se l'organizzazione lo consente. In caso di un utente non Office 365, è possibile leggere e rispondere ai messaggi crittografati sul web tramite il web browser.
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>I tipi di file supportati come allegati a messaggi di posta elettronica protette? Allegati ereditano i criteri di protezione associati a messaggi di posta elettronica protette?

È possibile allegare qualsiasi tipo di file per posta protetto, ma solo per il file formati indicato [di seguito](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)vengono applicati i criteri di protezione. 
  
Se un formato di file è supportato, ad esempio un file di Word, Excel o PowerPoint, il file è sempre protetto, anche dopo l'allegato è stato scaricato dal destinatario. Ad esempio, un allegato viene protetta tramite non inoltrare, se il destinatario originale download e inoltra l'allegato a un nuovo destinatario, il nuovo destinatario non sarà in grado di aprire il file protetto.
  
## <a name="are-pdf-file-attachments-supported"></a>Allegati di file PDF sono supportati?

Se si associa un file PDF a un messaggio protetto, il messaggio direttamente verrà protetto, ma non verrà applicata alcuna protezione aggiuntive al file PDF dopo che il destinatario ha ricevuto lo. Ciò significa che il destinatario può Salva con nome, Forward, copia e stampa il file PDF.
  
## <a name="are-onedrive-for-business-attachments-supported"></a>Sono OneDrive per gli allegati Business supportati?

Non ancora. OneDrive per gli allegati Business non sono supportati e gli utenti finali non possono crittografare un messaggio contenente un cloud OneDrive per allegato Business.
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>È possibile automaticamente crittografare i messaggi dalla configurazione dei criteri?

Sì. Utilizzo di regole del flusso di posta elettronica di Exchange Online per crittografare automaticamente un messaggio in base a determinate condizioni. Ad esempio, è possibile creare criteri basati sul destinatario ID, il dominio del destinatario, o del contenuto nel corpo o l'oggetto del messaggio. Vedere [definire regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>È possibile automaticamente crittografare i messaggi dalla configurazione dei criteri in dati di prevenzione della perdita (DLP) tramite la sicurezza &amp; centro conformità?

Attualmente è possibile solo impostare le regole del flusso di posta elettronica di Exchange Online. Crittografia non è supportata in DLP attraverso la sicurezza &amp; centro conformità.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>È possibile personalizzare i messaggi crittografati con il marchio della società?

Sì! Per informazioni sulla personalizzazione dei messaggi di posta elettronica e il portale OME, vedere Aggiunta del marchio dell'organizzazione ai messaggi crittografati. Vedere [aggiungere marchio dell'organizzazione per i messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Sono disponibili le funzionalità o sui concetti di messaggi di posta elettronica crittografati report?

Non al momento, ma disponibile a breve.
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>È possibile utilizzare la crittografia dei messaggi con funzionalità di conformità, ad esempio eDiscovery?

Sì. Tutti i messaggi di posta elettronica crittografati sono individuabili da funzionalità di conformità di Office 365.
  

