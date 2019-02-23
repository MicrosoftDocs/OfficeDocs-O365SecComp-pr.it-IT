---
title: Configurare le nuove funzionalità di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection, l'organizzazione può utilizzare le comunicazioni di posta elettronica protette con persone all'interno e all'esterno dell'organizzazione. Le nuove funzionalità OME sono compatibili con altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: eddafca15fa4efdd3f929145e7933a3b7dfb5f27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220646"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurare le nuove funzionalità di Office 365 Message Encryption

Con le nuove funzionalità di crittografia dei messaggi di Office 365, che sfruttano le funzionalità di protezione di Azure Information Protection, l'organizzazione può facilmente condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono inviare e ricevere messaggi protetti con altre organizzazioni di Office 365, nonché clienti non di Office 365 che utilizzano Outlook.com, Gmail e altri servizi di posta elettronica.

||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>Informazioni introduttive su OME tramite l'attivazione di Azure Rights Management, parte di Azure Information Protection

È ora facile iniziare a utilizzare le nuove funzionalità OME. Dal febbraio 2018, Office 365 attiva automaticamente le nuove funzionalità OME per le organizzazioni idonee all'interno dei data center. L'organizzazione è idonea se si tratta di un nuovo tenant di Office 365 e l'organizzazione dispone delle sottoscrizioni appropriate. **Se è stata abilitaTa Azure Rights Management (Azure RMS), parte di Azure Information Protection, viene abilitata automaticamente la crittografia dei messaggi di Office 365.** Non è necessario eseguire altre operazione per abilitare OME. Per attivare Azure Rights Management, vedere [attivazione di Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). Per informazioni sulle sottoscrizioni, vedere "quali abbonamenti sono necessari per utilizzare il nuovo OME capabilities?" nelle [domande frequenti sulla crittografia dei messaggi di Office 365](ome-faq.md). Per informazioni sull'acquisto di una sottoscrizione a Azure Information Protection, vedere [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).
  
Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare immediatamente queste nuove funzionalità. Al contrario, è necessario eseguire la migrazione da AD RMS a Azure Information Protection per primo. Dopo aver completato la migrazione, è possibile eseguire correttamente questa procedura.
  
Se si sceglie di continuare a utilizzare AD RMS locale con Exchange Online invece di eseguire la migrazione a Azure Information Protection, non sarà possibile utilizzare queste nuove funzionalità.
  
## <a name="how-the-new-capabilities-for-ome-work"></a>Come funzionano le nuove funzionalità di OME

Le nuove funzionalità di crittografia dei messaggi di Office 365 utilizzano le funzionalità di protezione, denominate anche Azure Rights Management (Azure RMS), da Azure Information Protection. Sono inclusi i criteri di crittografia, identità e autorizzazione che consentono di proteggere il messaggio di posta elettronica. È possibile crittografare i messaggi utilizzando i modelli Rights Management, l' [opzione](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)non inoltrare e l' [opzione solo crittografia](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). Gli utenti possono quindi crittografare i messaggi di posta elettronica e una vasta gamma di allegati di Office 365 utilizzando queste opzioni. Per un elenco completo dei tipi di allegati supportati, vedere ["tipi di file coperti da criteri IRM quando sono allegati ai messaggi" in Introduzione a IRM per i messaggi di posta elettronica](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). In qualità di amministratore, è anche possibile definire le regole del flusso di posta per applicare la protezione. Ad esempio, è possibile definire una regola in cui tutti i messaggi non protetti indirizzati a un destinatario specifico o che contengono parole specifiche nella riga dell'oggetto sono protetti da accessi non autorizzati e i destinatari non possono copiare o stampare il contenuto del messaggio.
  
A differenza della versione precedente di OME, queste nuove funzionalità forniscono un'esperienza di mittente unificata se si sta inviando posta all'interno dell'organizzazione o ai destinatari esterni a Office 365. Inoltre, i destinatari che ricevono un messaggio di posta elettronica protetto inviato a un account di Office 365 in Outlook 2016 o Outlook sul Web, non è necessario eseguire ulteriori operazioni per visualizzare il messaggio. Funziona perfettamente. Anche i destinatari che utilizzano client di posta elettronica e provider di servizi di posta elettronica dispongono di un'esperienza migliorata. Per informazioni, vedere [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e [come aprire un messaggio protetto](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Per un elenco dettagliato delle differenze tra la versione precedente di OME e le nuove funzionalità OME, vedere [compare versions of ome](ome-version-comparison.md).
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>Procedura per configurare manualmente le nuove funzionalità di OME

Le nuove funzionalità OME sono abilitate automaticamente per la maggior parte delle organizzazioni di Office 365. Se l'organizzazione non ha automaticamente abilitato OME, o se è stata attivata la nuova funzionalità OME, eseguire la procedura seguente per configurare manualmente le nuove funzionalità di OME.
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>Per impostare manualmente le nuove funzionalità di OME

1. Verificare di disporre dell'abbonamento appropriato per la propria organizzazione. Per informazioni sulle sottoscrizioni, vedere "quali abbonamenti sono necessari per utilizzare il nuovo OME capabilities?" nelle [domande frequenti sulla crittografia dei messaggi di Office 365.](ome-faq.md) Per informazioni sull'acquisto di una sottoscrizione a Azure Information Protection, vedere [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

2. Decidere se si desidera gestire la chiave radice per Azure Information Protection (impostazione predefinita) o generare e gestire manualmente questa chiave (ovvero portare la propria chiave o BYOK). Se si desidera generare e gestire manualmente questa chiave, è necessario completare alcuni passaggi prima di configurare le nuove funzionalità di OME. Per ulteriori informazioni, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Microsoft consiglia di eseguire questa procedura prima di configurare OME.

3. Abilitare le nuove funzionalità di OME attivando Azure Rights Management. Per istruzioni, vedere [attivazione di Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). Quando si esegue questa operazione, Office 365 attiva automaticamente le nuove funzionalità OME.

    > [!TIP]
    > Outlook sul Web memorizza nella cache la propria interfaccia utente, quindi è consigliabile attendere un giorno prima di provare a applicare le nuove funzionalità di OME ai messaggi di posta elettronica utilizzando il client. Prima che gli aggiornamenti dell'interfaccia utente riflettano la nuova configurazione, le nuove funzionalità di OME non saranno disponibili. Dopo l'aggiornamento dell'interfaccia utente, gli utenti possono proteggere i messaggi di posta elettronica utilizzando le nuove funzionalità di OME.
  
4. Optional Impostare nuove regole del flusso di posta o aggiornare le regole del flusso di posta esistenti che definiscono come e quando si desidera che Office 365 crittografa i messaggi inviati dall'organizzazione.

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>Verificare che le nuove funzionalità di OME siano configurate correttamente utilizzando Windows PowerShell

Eseguire la procedura seguente per verificare che il tenant sia configurato correttamente per l'utilizzo delle nuove funzionalità di OME tramite Exchange Online PowerShell.
  
1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Test-IRMConfiguration utilizzando la sintassi seguente:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   Ad esempio:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

    Dove indirizzo di posta elettronica è l'indirizzo di posta elettronica di un utente nell'organizzazione di Office 365. Se facoltativo, l'indirizzo di posta elettronica del mittente consente di forzare il sistema a eseguire ulteriori controlli. I risultati devono essere simili ai seguenti:

     ```text
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

    Dove *Contoso* viene sostituito con il nome dell'organizzazione di Office 365.

    I nomi dei modelli predefiniti restituiti nei risultati possono essere diversi da quelli visualizzati nei risultati sopra riportati.

    Per un'introduzione ai modelli e alle informazioni sui modelli predefiniti, vedere [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Per informazioni sull'opzione non inoltrare, l'opzione solo crittografia e su come creare modelli aggiuntivi o individuare quali diritti sono inclusi in un modello esistente, vedere Configuring [Usage Rights for Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).

3. Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>Passaggi successivi: definire nuove regole del flusso di posta che utilizzano le nuove funzionalità OME

Questo passaggio è facoltativo per le nuove distribuzioni OME, tuttavia, questo passaggio è necessario per le distribuzioni OME esistenti che già dispongono di regole del flusso di posta impostate per crittografare la posta in uscita. Se si desidera sfruttare le nuove funzionalità OME, è necessario aggiornare le regole del flusso di posta esistenti. In caso contrario, gli utenti continueranno a ricevere messaggi di posta elettronica crittografati che utilizzano il formato di allegato HTML precedente anziché la nuova esperienza OME senza problemi.
  
Le regole del flusso di posta determinano in quali condizioni devono essere crittografati i messaggi di posta elettronica, nonché le condizioni per la rimozione della crittografia. Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati quando vengono inviati.
  
Per ulteriori informazioni sulle regole del flusso di posta, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Inviare, visualizzare e rispondere a messaggi crittografati in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[Enable-Aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Connessione a Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md)
