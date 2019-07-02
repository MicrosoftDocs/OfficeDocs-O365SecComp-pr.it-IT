---
title: Domande frequenti sulla crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Domande su come funzionano le nuove funzionalità di protezione dei messaggi di Office 365? Controllare la risposta qui.
ms.openlocfilehash: 1625ecd3f2c7991e2726539bcfa0c772d1ffea59
ms.sourcegitcommit: 803baca9f99a6691fb41a3308e799752e4d8f20c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222260"
---
# <a name="office-365-message-encryption-faq"></a>Domande frequenti su Office 365 Message Encryption

Domande su come funzionano le nuove funzionalità di protezione dei messaggi di Office 365? Controllare la risposta qui. Inoltre, vedere le [domande frequenti sulla protezione dei dati in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) per le risposte alle domande sul servizio di protezione dei dati, Azure Rights Management, in Azure Information Protection.

||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>Che cos'è la crittografia dei messaggi (OME) di Office 365?

OME combina la crittografia della posta elettronica e le funzionalità di gestione dei diritti. Le funzionalità di Rights management si basano sulla tecnologia Azure Information Protection.
  
## <a name="who-can-use-ome"></a>Chi può utilizzare OME?

È possibile utilizzare le nuove funzionalità di OME nelle condizioni seguenti:
  
- Se non è stato mai configurato OME o IRM per Exchange online in Office 365.

- Se sono stati configurati OME e IRM, è possibile utilizzare questi passaggi se si utilizza il servizio Azure Rights Management da Azure Information Protection.

- Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare immediatamente queste nuove funzionalità. Al contrario, è necessario [migrare ad RMS in Azure Information Protection per](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primo. Dopo aver completato la migrazione, è possibile configurare correttamente OME.

    Se si sceglie di continuare a utilizzare AD RMS locale con Exchange Online invece di eseguire la migrazione a Azure Information Protection, non sarà possibile utilizzare queste nuove funzionalità.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Quali abbonamenti sono necessari per utilizzare le nuove funzionalità OME?

Per utilizzare le nuove funzionalità OME, è necessario uno dei seguenti piani:
  
- La crittografia dei messaggi di Office 365 è disponibile come parte di Office 365 Enterprise E3 ed E5, Microsoft Enterprise E3 ed E5, Microsoft 365 business, Office 365 a1, a3 e a5 e Office 365 Government G3 e G5. I clienti non necessitano di licenze aggiuntive per ricevere le nuove funzionalità di protezione alimentate da Azure Information Protection.

- È inoltre possibile aggiungere Azure Information Protection Plan 1 ai piani seguenti per ricevere le nuove funzionalità di crittografia dei messaggi di Office 365: Exchange Online piano 1, Exchange Online piano 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium o Office 365 Enterprise E1.

- Tutti gli utenti che usufruiscono della crittografia dei messaggi di Office 365 devono essere concessi in licenza per essere coperti dalla caratteristica.

- Per l'elenco completo, vedere le [descrizioni dei servizi di Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) per la crittografia dei messaggi di Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>È possibile utilizzare Exchange Online con Bring your own key (BYOK) in Azure Information Protection?

Sì! Microsoft consiglia di completare la procedura di configurazione di BYOK prima di configurare OME.
  
Per ulteriori informazioni su BYOK, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>L'approccio di Microsoft alle richieste di dati di terze parti, ad esempio le citazioni, è stato modificato da OME e BYOK con Azure Information Protection?

No. OME e l'opzione per fornire e controllare le proprie chiavi di crittografia, denominate BYOK, da Azure Information Protection non sono state progettate per rispondere alle citazioni di polizia. OME, con BYOK per Azure Information Protection, è stato ideato per i clienti con conformità. Microsoft richiede molto sul serio le richieste di terze parti per i dati dei clienti. Come provider di servizi cloud, è sempre favorevole alla privacy dei dati del cliente. Nel caso in cui venga visualizzato un mandato di comparizione, si cerca sempre di reindirizzare la terza parte al cliente per ottenere le informazioni. (Leggere il Blog di Brad Smith: [proteggere i dati dei clienti dallo spionaggio governativo](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Pubblicheremo periodicamente informazioni dettagliate sulla richiesta ricevuta. Per ulteriori informazioni sulle richieste di dati di terze parti, vedere Redirecting [to government and Law Enforcement richieste to Access Customer data](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) on the Microsoft Trust Center. Vedere inoltre la sezione relativa alla divulgazione dei dati del cliente nelle [condizioni di servizi online (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>In che modo questa funzionalità è correlata alle funzionalità di crittografia dei messaggi di Office 365 (OME) e Information Rights Management (IRM) legacy?

Le nuove funzionalità per la crittografia dei messaggi di Office 365 rappresentano un'evoluzione delle soluzioni IRM e Legacy OME esistenti. Nella tabella seguente sono disponibili ulteriori dettagli.
  
**Confronto tra le funzionalità OME legacy, IRM e nuove OME**

|**Funzionalità**|**Versioni precedenti di OME**|**IRM**|**Nuove funzionalità OME**|
|:-----|:-----|:-----|:-----|
|**Invio di un messaggio di posta elettronica crittografato**|Solo tramite le regole del flusso di posta di Exchange|L'utente finale è stato avviato da Outlook per PC, Outlook per Mac o Outlook sul Web. o tramite le regole del flusso di posta di Exchange|L'utente finale è stato avviato da Outlook per PC, Outlook per Mac o Outlook sul Web. o tramite le regole del flusso di posta|
|**Gestione dei diritti**|-|Non inoltrare l'opzione e i modelli personalizzati|Opzione non inoltrare, opzione solo crittografia, modelli predefiniti e personalizzati|
|**Tipo di destinatario supportato**|Solo destinatari esterni|Solo destinatari interni|Destinatari interni ed esterni|
|**Esperienza per il destinatario**|I destinatari esterni hanno ricevuto un messaggio HTML che hanno scaricato e aperto in un browser o in un'app per dispositivi mobili scaricati.|I destinatari interni hanno ricevuto solo messaggi di posta elettronica crittografati in Outlook per PC, Outlook per Mac e Outlook sul Web.|I destinatari interni ed esterni ricevono messaggi di posta elettronica in Outlook per PC, Outlook per Mac, Outlook sul Web, Outlook per Android e Outlook per iOS oppure tramite un portale Web, indipendentemente dal fatto che siano o meno presenti nella stessa organizzazione di Office 365 o in qualsiasi ufficio 365 organizzazione. Il portale OME non richiede alcun download separato.|
|**Portare il proprio supporto chiave**|Non disponibile|Non disponibile| BYOK supportato|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Come si abilitano le nuove funzionalità OME per la propria organizzazione?

Vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md).
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>La versione precedente di OME sarà obsoleta?

È comunque possibile utilizzare la versione precedente di OME, non sarà deprecata in questo momento. Tuttavia, si consiglia vivamente alle organizzazioni di utilizzare la nuova e migliorata soluzione OME. I clienti che non sono già stati distribuiti OME non possono configurare una nuova distribuzione della versione precedente di OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>L'organizzazione utilizza Active Directory Rights Management, è possibile utilizzare questa funzionalità?

No. Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare immediatamente queste nuove funzionalità. Al contrario, è necessario [migrare ad RMS in Azure Information Protection per](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) primo. 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>L'organizzazione dispone di una distribuzione ibrida di Exchange. È possibile utilizzare questa funzionalità?

Gli utenti locali possono inviare messaggi crittografati tramite le regole del flusso di posta di Exchange Online. Per eseguire questa operazione, è necessario instradare la posta elettronica tramite Exchange Online. Per ulteriori informazioni, vedere [parte 2: configurare il flusso di posta dal server di posta elettronica a Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Quale client di posta elettronica è necessario utilizzare per creare un messaggio crittografato OME? Quali applicazioni sono supportate per l'invio di messaggi protetti?

È possibile creare messaggi protetti da Outlook 2016 e Outlook 2013 per PC e Mac e da Outlook sul Web.
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Quali client di posta elettronica sono supportati per la lettura e la risposta ai messaggi di posta elettronica protetti?

È possibile leggere e rispondere da Outlook per PC e Mac (2013 e 2016), Outlook sul Web e Outlook Mobile (Android e iOS) se si è un utente di Office 365. È inoltre possibile utilizzare il client di posta elettronica nativo iOS se l'organizzazione lo consente. Se non si è un utente di Office 365, è possibile leggere e rispondere a messaggi crittografati sul Web tramite il Web browser.
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Quali tipi di file sono supportati come allegati nei messaggi di posta elettronica protetti? Gli allegati ereditano i criteri di protezione associati ai messaggi di posta elettronica protetti?

È possibile allegare qualsiasi tipo di file a un messaggio protetto, tuttavia i criteri di protezione vengono applicati solo nei formati di file menzionati in [questo](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)articolo. 
  
Se è supportato un formato di file, ad esempio un file di Word, Excel o PowerPoint, il file è sempre protetto, anche dopo che l'allegato è stato scaricato dal destinatario. Ad esempio, se un allegato è protetto da non inoltrare e il destinatario originale Scarica e inoltra l'allegato a un nuovo destinatario, il nuovo destinatario non sarà in grado di aprire il file protetto.
  
## <a name="are-pdf-file-attachments-supported"></a>Gli allegati di file PDF sono supportati?

Se si collega un file PDF a un messaggio protetto, il messaggio verrà protetto, ma non verrà applicata alcuna protezione aggiuntiva al file PDF dopo che il destinatario lo ha ricevuto. Questo significa che il destinatario può salvare come, inoltrare, copiare e stampare il file PDF.
  
## <a name="are-onedrive-for-business-attachments-supported"></a>Gli allegati di OneDrive for business sono supportati?

Not yet. Gli allegati di OneDrive for business non sono supportati e gli utenti finali non possono crittografare un messaggio di posta elettronica che contiene un allegato cloud OneDrive for business.
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>È possibile crittografare automaticamente i messaggi impostando i criteri?

Sì. Utilizzare le regole del flusso di posta in Exchange Online per crittografare automaticamente un messaggio in base a determinate condizioni. Ad esempio, è possibile creare criteri basati sull'ID destinatario, sul dominio del destinatario o sul contenuto del corpo o dell'oggetto del messaggio. Vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>È possibile crittografare automaticamente i messaggi mediante l'impostazione di criteri di prevenzione della perdita di dati ( &amp; DLP) tramite il Centro sicurezza e conformità?

Sì! È possibile configurare le regole del flusso di posta in Exchange Online o utilizzando DLP nel centro &amp; sicurezza e conformità.
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>È possibile aprire i messaggi crittografati inviati a una cassetta postale condivisa?

I messaggi attualmente crittografati non sono supportati per una cassetta postale condivisa.

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>È possibile personalizzare i messaggi crittografati con il marchio dell'azienda?

Sì! Per informazioni sulla personalizzazione dei messaggi di posta elettronica e del portale OME, vedere Aggiungere il marchio dell'organizzazione ai messaggi crittografati. Vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Esistono funzionalità di creazione di report o Insight per i messaggi di posta elettronica crittografati?

È presente un rapporto di crittografia nel centro sicurezza e conformità. Vedere [visualizzare i report sulla sicurezza della posta elettronica nel centro sicurezza & Compliance.](view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>È possibile utilizzare la crittografia dei messaggi con funzionalità di conformità, ad esempio eDiscovery?

Sì. Tutti i messaggi di posta elettronica crittografati sono individuabili dalle funzionalità di conformità di Office 365.
