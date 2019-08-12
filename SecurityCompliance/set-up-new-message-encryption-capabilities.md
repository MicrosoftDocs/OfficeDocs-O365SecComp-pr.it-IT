---
title: Configurare le nuove funzionalità di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Con le nuove funzionalità di Office 365 Message Encryption predefinite in Azure Information Protection, l'organizzazione può usare la comunicazione tramite posta elettronica protetta con le persone interne ed esterne all'organizzazione. Le nuove funzionalità OME funzionano con le altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854800"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurare le nuove funzionalità di Office 365 Message Encryption

Le nuove funzionalità di Office 365 Message Encryption (OME) consentono alle organizzazioni di condividere la posta elettronica protetta con qualsiasi dispositivo. Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Office 365, oltre che con clienti non di Office 365 che usano Outlook.com, Gmail e altri servizi di posta elettronica.

||
|:-----|
|Questo articolo fa parte di una serie di articoli più ampia relativa a Office 365 Message Encryption. Quest’articolo è destinato ad amministratori e professionisti IT. Per informazioni sull'invio o sulla ricezione di un messaggio crittografato, vedere l'elenco di articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo più adatto alle proprie esigenze. |
||

Seguire questa procedura per verificare che le nuove funzionalità di OME siano disponibili nell'organizzazione di Office 365.

## <a name="verify-that-azure-rights-management-is-active"></a>Verificare che Azure Rights Management sia attivo

Le nuove funzionalità di OME sfruttano le caratteristiche di protezione di Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/it-IT/azure/information-protection/what-is-information-protection), la tecnologia usata da [Azure Information Protection](https://docs.microsoft.com/it-IT/azure/information-protection/what-is-azure-rms) per proteggere i messaggi di posta elettronica e i documenti tramite crittografia e controlli di accesso.

L'unico requisito necessario per usare le nuove funzionalità di OME è che [Azure Rights Management](https://docs.microsoft.com/it-IT/azure/information-protection/what-is-azure-rms) debba essere attivato nel tenant dell'organizzazione. In tal caso, Office 365 attiva automaticamente le nuove funzionalità di OME e non è necessario eseguire alcuna operazione.

Azure RMS viene attivato automaticamente anche per la maggior parte dei piani idonei, pertanto non è necessario eseguire alcuna operazione a tal riguardo. Per altre informazioni, vedere [Attivazione di Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service).

>[!IMPORTANT]
>Se si usa Active Directory Rights Management Services (AD RMS) con Exchange Online, è necessario eseguire la migrazione ad Azure Information Protection](https://docs.microsoft.com/it-IT/azure/information-protection/migrate-from-ad-rms-to-azure-rms) prima di poter usare le nuove funzionalità di OME. OME non è compatibile con AD RMS.  

Per ulteriori informazioni, vedere:

- [Quali abbonamenti sono necessari per usare le nuove funzionalità di OME? ](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) per verificare se il piano di abbonamento include Azure Information Protection (che include le funzionalità di Azure RMS).
- Per informazioni sull'acquisto di un abbonamento idoneo, vedere [Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/).  

### <a name="manually-activating-azure-rights-management"></a>Attivazione manuale di Azure Rights Management

Se è stato disabilitato Azure RMS o se non è stato attivato automaticamente, è possibile attivarlo manualmente in:

- Interfaccia di amministrazione di Microsoft 365**: per istruzioni, vedere [Come attivare Azure Rights Management dall'interfaccia di amministrazione](https://docs.microsoft.com/it-IT/azure/information-protection/activate-office365).
- **Portale di Azure**: per istruzioni, vedere [Come attivare Azure Rights Management dal Portale di Azure](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure).

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurare la gestione della chiave tenant di Azure Information Protection

Questo passo è facoltativo. La gestione della chiave radice di Azure Information Protection da parte di Microsoft è un’impostazione predefinita e la procedura consigliata per la maggior parte dei tenant di Office 365. Se questo è il caso, non è necessario eseguire alcuna operazione.

Ci sono diversi motivi, ad esempio i requisiti di conformità, che possono richiedere di generare e gestire una chiave radice, nota anche come bring your own key (BYOK). In questo caso, è consigliabile completare i passaggi necessari prima di configurare le nuove funzionalità di OME. Per altre informazioni, vedere [Pianificazione e implementazione della chiave tenant di Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Verificare la nuova configurazione di OME in PowerShell di Exchange Online

È possibile verificare se il tenant di Office 365 sia configurato correttamente per l'uso delle nuove funzionalità di OME disponibili in [PowerShell di Exchange Online](https://docs.microsoft.com/it-IT/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
  
1. Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/it-IT/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando un account con autorizzazioni di amministratore globale nel tenant di Office 365.

2. Eseguire il cmdlet Get-IRMConfiguration.

     Dovrebbe essere visualizzato un valore di $True per il parametro AzureRMSLicensingEnabled, che indica che OME è configurato nel tenant. Se non lo è, usare Set-IRMConfiguration per impostare il valore di AzureRMSLicensingEnabled su $True per abilitare OME.

3. Eseguire il cmdlet Test-IRMConfiguration usando la sintassi seguente:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Esempio**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - L'inserimento di un indirizzo di posta elettronica del mittente è facoltativo, ma forza il sistema a eseguire ulteriori controlli. Usare l'indirizzo di posta elettronica di un utente nel tenant di Office 365.

     Il risultato dovrebbe essere simile al seguente:

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

   - Il nome dell'organizzazione di Office 365 sostituisce *Contoso*.

   - I nomi dei modelli predefiniti potrebbero essere diversi rispetto a quelli visualizzati in precedenza. Per altre informazioni, vedere [Configurazione e gestione dei modelli per Azure Information Protection](https://docs.microsoft.com/it-IT/azure/information-protection/configure-policy-templates).

4. Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Passaggi successivi: definire le regole del flusso di posta per usare le nuove funzionalità di OME

Se in precedenza sono state configurate regole del flusso di posta per crittografare la posta elettronica nell'organizzazione di Office 365, è necessario aggiornare le regole esistenti per usare le nuove funzionalità di OME. Per le nuove distribuzioni, è necessario creare nuove regole per il flusso di posta.

>[!IMPORTANT]
>In caso contrario, gli utenti continueranno a ricevere messaggi crittografati che usano il formato dell'allegato HTML precedente invece della nuova esperienza di OME.

Le regole del flusso di posta elettronica determinano le condizioni con cui i messaggi di posta elettronica devono essere crittografati e le condizioni per rimuovere la crittografia. Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati al momento dell'invio.
  
Per altre passaggi sulla creazione delle regole del flusso di posta elettronica di OME, vedere [Definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

Aggiornare le regole esistenti per usare le nuove funzionalità di OME:

1. Nell'interfaccia di amministrazione di Microsoft 365, passare a **Interfacce di amministrazione > Exchange**.
2. Nell'interfaccia di amministrazione di Exchange, passare a **Flusso di posta > Regole**.
3. Per ogni regola, in **Fai quanto segue**:
    - Selezionare **Modifica la sicurezza del messaggio**.
    - Selezionare Applica Office 365 Message Encryption e la protezione tramite diritti**.
    - Selezionare un modello RMS dall'elenco.
    - Selezionare **Salva**.
    - Selezionare **OK**.
