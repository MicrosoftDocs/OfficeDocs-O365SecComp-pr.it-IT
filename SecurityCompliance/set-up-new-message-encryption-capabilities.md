---
title: Configurare le nuove funzionalità di crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Nuovo Office 365 Message Encryption funzionalità basate sul Azure Information Protection dell'organizzazione possono utilizzare protetti comunicazioni di posta elettronica con persone interne o esterne all'organizzazione. Le nuove funzionalità OME funziona con altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: c24b2f9b612b863217df8afd951424d1a89295c9
ms.sourcegitcommit: d89c24258123a3ffde574a391d59afd3aea8470d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "23955418"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurare le nuove funzionalità di crittografia dei messaggi di Office 365

Con le nuove funzionalità di Office 365 messaggio crittografia (OME), che utilizza la funzionalità di protezione in Azure Information Protection, l'organizzazione può condividere facilmente posta protetto con tutti gli utenti con qualsiasi dispositivo. Gli utenti possono inviare e ricevere messaggi protetti con altre organizzazioni di Office 365, nonché i clienti non Office 365 che utilizzano Outlook.com, Gmail e altri servizi di posta elettronica.
  
## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>Guida introduttiva a OME attivando Azure Rights Management, parte della protezione delle informazioni di Azure

È ora più semplice acquisire familiarità con le nuove funzionalità OME. A partire da febbraio 2018, Office 365 attiva automaticamente le nuove funzionalità OME per le organizzazioni idonei entro i centri dati. L'organizzazione è idonea se si tratta di un nuovo tenant di Office 365 e l'organizzazione ha le sottoscrizioni appropriate. **Se è stata abilitata Azure Rights Management (RMS) Azure, parte di Azure Information Protection, quindi è attiva automaticamente Office 365 Message Encryption automaticamente.** Non è necessario eseguire alcuna operazione per abilitare OME. Per attivare Azure Rights Management, vedere [Attivazione di Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). Per informazioni sulle sottoscrizioni, vedere "le sottoscrizioni è necessario utilizzare il nuovo capabilities? OME" in [Domande frequenti su crittografia dei messaggi di Office 365](ome-faq.md). Per informazioni sull'acquisto di una sottoscrizione per la protezione delle informazioni di Azure, vedere [La protezione delle informazioni di Azure](https://azure.microsoft.com/services/information-protection/).
  
Se si utilizza Exchange Online con il servizio Active Directory Rights Management (AD RMS), sarà possibile abilitare queste nuove funzionalità immediatamente. In realtà, è necessario eseguire innanzitutto la migrazione da AD RMS per la protezione delle informazioni di Azure. Una volta completata la migrazione, è possibile eseguire correttamente la procedura seguente.
  
Se si sceglie di continuare a utilizzare locale AD RMS con Exchange Online anziché la migrazione per la protezione delle informazioni di Azure, non sarà in grado di utilizzare queste nuove funzionalità.
  
## <a name="how-the-new-capabilities-for-ome-work"></a>Funzionamento delle nuove funzionalità per OME

Le nuove funzionalità di Office 365 Message Encryption utilizzare funzionalità di protezione, denominata anche Azure Rights Management (RMS) Azure, dalla protezione delle informazioni di Azure. Sono inclusi i criteri di crittografia, identity e l'autorizzazione per proteggere la posta elettronica. È possibile crittografare i messaggi con i modelli di gestione dei diritti di utilizzo, l' [opzione non inoltrare](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)e l' [opzione solo crittografare](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). Gli utenti possono quindi crittografare i messaggi di posta elettronica e un'ampia gamma di allegati di Office 365, utilizzando le opzioni. Per un elenco completo dei tipi di allegati supportati, vedere ["tipi di File a cui i criteri IRM quando sono allegate ai messaggi" in Introduzione a IRM per i messaggi di posta elettronica](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). In qualità di amministratore, è inoltre possibile definire regole del flusso di posta elettronica per applicare la protezione. Ad esempio, è possibile definire una regola in tutti i messaggi non protetti che si basano a un destinatario specifico o contenenti parole specifiche nella riga dell'oggetto sono protetti dall'accesso non autorizzato, e i destinatari non possono copiare o stampare il contenuto del messaggio.
  
A differenza della versione precedente di OME, queste nuove funzionalità offrono un'esperienza unificata mittente se si invia posta all'interno dell'organizzazione o ai destinatari all'esterno di Office 365. Destinatari del messaggio di posta elettronica protetta inviati a un account di Office 365 2016 Outlook o Outlook sul web, inoltre, non è necessario eseguire alcuna azione aggiuntiva per visualizzare il messaggio. Funziona perfettamente. I destinatari utilizzando altri client di posta elettronica e provider di servizi di posta elettronica inoltre dispongono di un'esperienza migliorata. Per informazioni, vedere [informazioni sui messaggi protetti in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e [come aprire un messaggio protetto](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>Passaggi per impostare manualmente le nuove funzionalità per OME

Se l'organizzazione non dispone automaticamente OME abilitata o se è attivata OME disattivata, eseguire la procedura seguente per impostare manualmente le nuove funzionalità per OME.
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>Per impostare manualmente le nuove funzionalità per OME

1. Verificare che la sottoscrizione appropriata per l'organizzazione. Per informazioni sulle sottoscrizioni, vedere "le sottoscrizioni è necessario utilizzare il nuovo capabilities? OME" nel [domande frequenti su crittografia dei messaggi di Office 365.](ome-faq.md) Per informazioni sull'acquisto di una sottoscrizione per la protezione delle informazioni di Azure, vedere [La protezione delle informazioni di Azure](https://azure.microsoft.com/services/information-protection/).
    
2. Decidere se Microsoft per gestire la chiave principale per la protezione delle informazioni di Azure (predefinito), o generare e gestire questa chiave familiarità (noto come portare in primo piano personalizzati chiave o BYOK). Se si desidera generare e la gestione di questa chiave manualmente, è necessario eseguire alcune operazioni prima di impostare le nuove funzionalità per OME. Per ulteriori informazioni, vedere [pianificazione e l'implementazione la chiave del tenant la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Si consiglia di eseguire la procedura seguente prima di impostare OME.
    
3. Abilitare le nuove funzionalità per OME attivando Azure Rights Management. Per ulteriori informazioni, vedere [Attivazione di Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). A tale scopo, Office 365 attiva automaticamente le nuove funzionalità OME automaticamente.
    
    > [!TIP]
    > Outlook sul Web memorizza nella cache relativa interfaccia utente, in modo da essere opportuno attendere un giorno prima di tentare di applicare le nuove funzionalità per OME ai messaggi di posta elettronica utilizzando questo client. Prima che l'interfaccia utente aggiornata per riflettere la nuova configurazione, le nuove funzionalità per OME non sarà disponibile. Dopo l'aggiornamento dell'interfaccia utente, gli utenti possono proteggere messaggi di posta elettronica utilizzando le nuove funzionalità per OME. 
  
4. (Facoltativo) Impostare le nuove regole di flusso di posta elettronica o aggiornare regole del flusso di posta elettronica esistente che definiscono come e quando si vuole che Office 365 per crittografare i messaggi inviati dall'organizzazione.
    
## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>Verificare che le nuove funzionalità per OME siano configurate correttamente tramite Windows PowerShell

Eseguire la procedura seguente per verificare che il tenant sia configurato correttamente per l'utilizzo delle nuove funzionalità per OME tramite Exchange Online PowerShell.
  
1. Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Eseguire il cmdlet Test-IRMConfiguration utilizzando la sintassi seguente:
    
    ```Test-IRMConfiguration [-Sender <email address >]```  

   Ad esempio:
    
    ```Test-IRMConfiguration -Sender securityadmin@contoso.com```

    Indirizzo di posta elettronica dove è l'indirizzo di posta elettronica di un utente nell'organizzazione Office 365. Mentre facoltativo, l'indirizzo di posta elettronica del mittente forza il sistema deve eseguire ulteriori verifiche.
    
    I risultati dovrebbero risultare come queste:
    
    ```
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.
            
            OVERALL RESULT: PASS
    ```

    Dove *Contoso* è stato sostituito con il nome dell'organizzazione Office 365. 
    
    I nomi dei modelli predefiniti nei risultati restituiti potrebbero essere diversi da quello visualizzato nei risultati della precedenti.
    
    Per avere un'introduzione ai modelli e informazioni sui modelli predefiniti, vedere [configurazione e gestione dei modelli per la protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni su non inoltrare l'opzione, crittografare sola opzione e come creare ulteriori modelli o Scopri tutto titolarità dei diritti sono inclusi in un modello esistente, vedere [configurazione di diritti di utilizzo per Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).
    
3. Eseguire il cmdlet Remove-PSSession per disconnettersi da Rights Management service.
    
    ```Remove-PSSession $session```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>Passaggi successivi: definire nuove regole di flusso di posta elettronica che utilizzano le nuove funzionalità OME
<a name="Rules_1"> </a>

Questo passaggio è facoltativo per le nuove distribuzioni OME, tuttavia, questo passaggio è obbligatorio per le distribuzioni OME esistenti che dispone già di regole del flusso di posta elettronica è impostate per crittografare la posta elettronica in uscita. Se si desidera usufruire delle nuove funzionalità OME, è necessario aggiornare le regole di flusso di posta elettronica esistente. In caso contrario, gli utenti continua a ricevere messaggi crittografati che utilizza il formato allegato HTML precedente anziché l'esperienza OME nuova e semplice.
  
Regole del flusso di posta elettronica determinano sotto il messaggio di posta elettronica le condizioni devono essere crittografati i messaggi, nonché alle condizioni per la rimozione di crittografia. Quando si imposta un'azione per una regola, i messaggi che soddisfano le condizioni regola vengono crittografati quando sei inviati.
  
Per ulteriori informazioni sulle regole di flusso di posta elettronica, vedere [definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Argomenti correlati
<a name="Rules_1"> </a>

[Invia, Visualizza e Rispondi ai messaggi crittografati in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[Enable-Aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Connessione a Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Definire regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md)
  

