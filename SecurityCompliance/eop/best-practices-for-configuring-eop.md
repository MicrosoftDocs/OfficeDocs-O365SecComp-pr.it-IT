---
title: Procedure consigliate per la configurazione di EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Seguire queste procedure consigliate per Exchange Online Protection (EOP) per eseguire una configurazione corretta ed evitare che si verifichino errori comuni.
ms.openlocfilehash: ef58e2cd5a3ffdbbeb02124442c355974d174073
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027273"
---
# <a name="best-practices-for-configuring-eop"></a>Procedure consigliate per la configurazione di EOP
  
Seguire queste procedure consigliate per Exchange Online Protection (EOP) per eseguire una configurazione corretta ed evitare che si verifichino errori comuni. Come regola generale, si consiglia di utilizzare le impostazioni di configurazione predefinite. In questo argomento si presuppone che il processo di installazione sia già stato completato. Se l'installazione di EOP non è stata completata, vedere [Installazione del servizio EOP](set-up-your-eop-service.md).
  
## <a name="use-a-test-domain"></a>Utilizzo di un dominio di prova

È opportuno utilizzare un dominio di prova, un sottodominio oppure un dominio di volume non elevato per provare le funzionalità del servizio prima di implementarle in domini con volumi di produzione maggiori.
  
## <a name="synchronize-recipients"></a>Sincronizzazione dei destinatari

Se nell'organizzazione sono già presenti account utente in un ambiente Active Directory locale, è possibile sincronizzare tali account con Azure Active Directory nel cloud. Si consiglia di utilizzare la sincronizzazione della directory. Per ulteriori informazioni sui vantaggi della sincronizzazione della directory e sulla procedura per impostarla, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>Personalizzazione del record SPF per prevenire spoofing

Quando si imposta di EOP, è stato aggiunto un record (framework criteri mittente) SPF per EOP per i record DNS. Il record SPF consente di impedire attacchi di spoofing. Per ulteriori informazioni su come un record SPF impedisce lo spoofing e come è possibile aggiungere gli indirizzi IP locale per il record SPF, vedere [impostare SPF in Office 365 per evitare attacchi di spoofing](../set-up-spf-in-office-365-to-help-prevent-spoofing.md). 
  
## <a name="set-anti-spam-options"></a>Impostazione delle opzioni di posta indesiderata

Gestisci la connessione delle impostazioni del filtro mediante l'aggiunta di indirizzi IP agli elenchi di indirizzi IP bloccati e indirizzi IP consentiti e selezionando l'opzione **Abilita elenco sicuro** , che dovrebbe ridurre il numero di falsi positivi (posta legittima classificata come posta indesiderata) viene visualizzato. Ulteriori informazioni, vedere [configurare il criterio di filtro di connessione](../configure-the-connection-filter-policy.md). Per ulteriori impostazioni di posta indesiderata che si applicano a tutta l'organizzazione, esaminare [per contribuire a garantire che un messaggio non è contrassegnato come posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=534224) o di [posta elettronica di blocco della posta indesiderata con il filtro posta indesiderata di Office 365 per evitare problemi negativi false](https://go.microsoft.com/fwlink/p/?LinkId=534225). Questi sono utili se si dispone di controllo a livello di amministratore e si desidera impedire falsi positivi o falsi negativi.
  
Gestire i filtri del contenuto per la revisione e se lo si desidera modificare le impostazioni predefinite. Ad esempio, è possibile modificare l'azione per cosa accade ai messaggi di rilevamento posta indesiderata. Se si desidera utilizzare un approccio aggressivo filtro posta indesiderata, è possibile configurare le opzioni di filtro della posta indesiderata. È consigliabile testare queste opzioni innanzitutto prima implementarle nell'ambiente di produzione (attivando la loro) si consiglia alle organizzazioni preoccupate phishing di attivare il **record SPF: riuscito** opzione. Ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](../configure-your-spam-filter-policies.md) e [Opzioni di filtro posta indesiderata](../advanced-spam-filtering-asf-options.md).
  
> [!IMPORTANT]
> Se si utilizza l'azione del filtro contenuto predefinito, **spostare il messaggio nella cartella posta indesiderata**, per assicurare che questa azione funzioneranno con cassette postali locali, è necessario configurare regole del flusso di posta elettronica Exchange, l'acronimo di regole di trasporto in locale Server per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [verificare che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
È consigliabile consultare le [domande frequenti sulla protezione anti-spam](../anti-spam-protection-faq.md), tra cui l'uscita sezione sulle procedure consigliate, che aiutano a garantire che la posta in uscita viene recapitata.
  
È possibile inviare falsi negativi (spam) e falsi positivi (non spam) a Microsoft per l'analisi in diversi modi. Per ulteriori informazioni, vedere [invio della posta indesiderata, posta non indesiderata e i messaggi di phishing phishing a Microsoft per l'analisi](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).
  
## <a name="set-anti-malware-options"></a>Impostazione delle opzioni antimalware

Revisione e l'ottimizzazione le impostazioni di filtro malware in center(EAC) di amministrazione di Exchange. Ulteriori informazioni, vedere [Configure anti-malware policies](../configure-anti-malware-policies.md). Si consiglia inoltre di lettura su altre domande e risposte relative alla protezione anti-malware nel nostro [domande frequenti sulla protezione Anti-malware ](../anti-malware-protection-faq-eop.md).
  
Se si teme che i file eseguibili possano contenere malware, è opportuno creare una regola del flusso di posta di Exchange che consente di bloccare tutti gli allegati contenenti contenuti eseguibili. Seguire i passaggi descritti in [Ridurre i pericoli di malware bloccando gli allegati di file in Exchange Online Protection](https://support.microsoft.com/kb/2959596) per bloccare i tipi di file elencati nella sezione "Tipi di file eseguibile supportati per la verifica della regola di trasporto" in [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).
  
È possibile utilizzare Filtro tipi di allegato comuni nell'interfaccia di amministrazione di Exchange. Selezionare **protezione** \> **filtri antimalware**. È possibile creare una regola del flusso di posta di Exchange, nota anche come regola di trasporto, che consente di bloccare gli allegati di posta elettronica con contenuti eseguibili. 
  
Per una maggiore protezione, si consiglia di utilizzare le regole del flusso di posta per bloccare alcune o tutte le seguenti estensioni: aade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. È possibile eseguire questa operazione utilizzando la condizione **Tutte le estensioni dei file allegati che includono le seguenti parole**. 
  
Gli amministratori e gli utenti finali possono segnalare malware che non sono stati rilevati dal filtro oppure un file che è stato erroneamente identificato come malware contattando Microsoft e richiedendo un'analisi. Per ulteriori informazioni, vedere [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
  
## <a name="create-mail-flow-rules"></a>Creazione di regole del flusso di posta

Creare regole del flusso di posta, dette anche regole di trasporto o filtri personalizzati, per soddisfare le proprie esigenze aziendali.
  
Quando si distribuisce una nuova regola alla produzione, selezionare prima una delle modalità di prova per verificare l'effetto della regola. Quando si è soddisfatti del funzionamento della regola, cambiare la modalità della regola in **Applica**.
  
Quando si distribuiscono nuove regole, prendere in considerazione l'aggiunta dell'azione aggiuntiva **Genera rapporto operazioni non consentite** per monitorare la regola in azione. 
  
In una configurazione ibrida, con parte dell'organizzazione in locale e parte in Office 365, è possibile creare regole che si applicano all'intera organizzazione. A tale scopo, utilizzare condizioni disponibili sia in locale che in Office 365. Anche se la maggior parte delle condizioni è disponibile in entrambe le distribuzioni, ne esistono alcune specifiche di un particolare scenario di distribuzione. Per ulteriori informazioni, vedere [Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).
  
Se si desidera, è possibile esaminare gli allegati di posta elettronica per i messaggi in transito all'interno dell'organizzazione impostando regole del flusso di posta. È possibile quindi eseguire un'azione sui messaggi presi in esame basandosi sui contenuti o sulle caratteristiche degli allegati. Per ulteriori informazioni, vedere [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).
  
### <a name="phishing-and-spoofing-prevention"></a>Prevenzione di phishing e spoofing

È possibile migliorare la protezione anti-phishing rilevando il momento in cui le informazioni personali escono dall'organizzazione nella posta elettronica. Ad esempio, è possibile utilizzare le seguenti espressioni regolari nelle regole del flusso di posta per rilevare la trasmissione di dati finanziari personali o informazioni che possono compromettere la privacy:
  
- \d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)
    
- \d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)
    
- \d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (qualsiasi numero di 16 cifre)
    
- \d\d\d\-\d\d\-\d\d\d\d (numeri della previdenza sociale)
    
È possibile ridurre la posta indesiderata e il phishing anche bloccando i messaggi di posta elettronica dannosi in ingresso che sembrano essere stati inviati dal proprio dominio. Ad esempio, è possibile creare una regola del flusso di posta che determina il rifiuto dei messaggi provenienti dal dominio dell'azienda e inviati allo stesso dominio dell'azienda per bloccare questo tipo di contraffazione del mittente.
  
> [!CAUTION]
> Si consiglia di creare questa regola di trasporto solo se si è certi che nessun messaggio di posta elettronica legittimo proveniente dal proprio dominio venga inviato da Internet al proprio server di posta. Ciò può accadere quando un messaggio viene inviato da un utente dell'organizzazione a un destinatario esterno e successivamente inoltrato a un altro destinatario dell'organizzazione. 
  
### <a name="extension-blocking"></a>Blocco delle estensioni

Se si è interessati sui file eseguibili che contiene malware, è possibile configurare i criteri antimalware per bloccare gli allegati di posta elettronica che ha contenuto eseguibile. Seguire i passaggi descritti in [Configure anti-malware policies](../configure-anti-malware-policies.md).
  
Per una maggiore protezione, si consiglia di bloccare alcune o tutte le seguenti estensioni: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.
  
## <a name="reporting-and-troubleshooting"></a>Segnalazione e risoluzione degli errori

Diagnosticare e risolvere tendenze e problemi generali utilizzando i rapporti nell'interfaccia di amministrazione di Office 365. Trovare i dati su un messaggio specifici di un singolo punto utilizzando lo strumento di traccia dei messaggi. Per ulteriori informazioni sulla segnalazione, vedere [Creazione di rapporti e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Per ulteriori informazioni sullo strumento di traccia dei messaggi, vedere [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Domande frequenti su EOP](eop-general-faq.md)
  
[Guida e supporto tecnico per EOP](help-and-support-for-eop.md)
  
[Video per iniziare con EOP](videos-for-getting-started-with-eop.md)
  
[Come assicurarsi che un messaggio non venga contrassegnato come indesiderato](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

