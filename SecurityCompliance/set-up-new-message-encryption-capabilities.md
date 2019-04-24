---
title: Configurare le nuove funzionalità di Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection, l'organizzazione può utilizzare le comunicazioni di posta elettronica protette con persone all'interno e all'esterno dell'organizzazione. Le nuove funzionalità OME sono compatibili con altre organizzazioni di Office 365, Outlook.com, Gmail e altri servizi di posta elettronica.
ms.openlocfilehash: ea8756d08b1c172c433d6cd8ad1752c4c7ad64e9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260754"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>Configurare le nuove funzionalità di Office 365 Message Encryption

Le nuove funzionalità di crittografia dei messaggi di Office 365 consentono alle organizzazioni di condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Office 365, nonché clienti non di Office 365 utilizzando Outlook.com, Gmail e altri servizi di posta elettronica.

||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e ai professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

Attenersi alla procedura riportata di seguito per verificare che le nuove funzionalità OME siano disponibili nell'organizzazione di Office 365.

## <a name="verify-that-azure-rights-management-is-active"></a>Verificare che Azure Rights Management sia attivo

Le nuove funzionalità OME sfruttano le funzionalità di protezione di Azure [Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), la tecnologia utilizzata da [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) per proteggere i messaggi di posta elettronica e i documenti tramite i controlli di accesso e crittografia.

L'unico prerequisito per l'utilizzo delle nuove funzionalità OME è che [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) deve essere attivato nel tenant dell'organizzazione. In caso contrario, Office 365 attiva automaticamente le nuove funzionalità OME e non è necessario eseguire alcuna operazione.

Azure RMS viene attivato automaticamente per la maggior parte dei piani idonei, quindi probabilmente non è necessario eseguire alcuna operazione anche in questo caso. Per ulteriori informazioni, vedere [attivazione di Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) .

>[!IMPORTANT]
>Se si utilizza Active Directory Rights Management Service (AD RMS) con Exchange Online, è necessario [eseguire la migrazione a Azure Information Protection prima di](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) poter utilizzare le nuove funzionalità ome. OME non è compatibile con AD RMS.  

Per ulteriori informazioni, vedere:

- [Quali abbonamenti sono necessari per utilizzare le nuove funzionalità ome?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) per verificare se il piano di sottoscrizione include Azure Information Protection (che include funzionalità di Azure RMS).
- [Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) per informazioni sull'acquisto di una sottoscrizione idonea.  

### <a name="manually-activating-azure-rights-management"></a>Attivazione manuale di Azure Rights Management

Se è stato disabilitato Azure RMS o se non è stato attivato automaticamente per qualsiasi motivo, è possibile attivarlo manualmente nel:

- Interfaccia di **amministrazione di office 365**: vedere [come attivare Azure Rights Management dall'interfaccia di amministrazione di Office 365](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) per istruzioni.
- **Portale di Azure**: vedere [come attivare Azure Rights Management dal portale di Azure](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) per istruzioni.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurare la gestione della chiave tenant di Azure Information Protection

Questo passo è facoltativo. L'impostazione predefinita e la procedura consigliata per la maggior parte dei tenant di Office 365 sono le impostazioni predefinite per la gestione della chiave radice per Azure Information Protection. In questo caso, non è necessario eseguire alcuna operazione.

Esistono diversi motivi, ad esempio i requisiti di conformità, che potrebbero richiedere la generazione e la gestione della chiave radice (nota anche come Bring your own key (BYOK)). In questo caso, è consigliabile completare i passaggi necessari prima di impostare le nuove funzionalità OME. Per ulteriori informazioni, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) .

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Verificare la nuova configurazione OME in Exchange Online PowerShell

È possibile verificare che il tenant di Office 365 sia configurato correttamente per l'utilizzo delle nuove funzionalità OME in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
  
1. [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) utilizzando un account con autorizzazioni di amministratore globale nel tenant di Office 365.

2. Eseguire il cmdlet Get-IRMConfiguration.

     Verrà visualizzato un valore $True per il parametro AzureRMSEnabled, che indica che OME è configurato nel tenant. In caso contrario, utilizzare Set-IRMConfiguration per impostare il valore di AzureRMSEnabled su $True per abilitare OME.

3. Eseguire il cmdlet Test-IRMConfiguration utilizzando la sintassi seguente:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Esempio**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - La disponibilità di un messaggio di posta elettronica del mittente è facoltativa, ma forza il sistema a eseguire ulteriori controlli. Utilizzare l'indirizzo di posta elettronica di qualsiasi utente nel tenant di Office 365.

     I risultati devono essere simili a:

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

   - Il nome dell'organizzazione di Office 365 sostituirà *Contoso*.

   - I nomi dei modelli predefiniti possono essere diversi da quelli visualizzati in alto. Per ulteriori informazioni, vedere Configuring [and Managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) .

4. Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Passaggi successivi: definire le regole del flusso di posta per l'utilizzo delle nuove funzionalità OME

Se sono già state configurate regole del flusso di posta per crittografare la posta elettronica nell'organizzazione di Office 365, è necessario aggiornare le regole esistenti per utilizzare le nuove funzionalità OME. Per le nuove distribuzioni, è necessario creare nuove regole del flusso di posta.

>[!IMPORTANT]
>Se non si aggiornano le regole del flusso di posta, gli utenti continueranno a ricevere messaggi di posta elettronica crittografati che utilizzano il formato di allegato HTML precedente, anziché la nuova esperienza di integrazione senza problemi.

Le regole del flusso di posta determinano in quali condizioni devono essere crittografati i messaggi di posta elettronica, nonché le condizioni per la rimozione della crittografia. Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati quando vengono inviati.
  
Per la procedura di creazione di regole del flusso di posta per OME, vedere [define Mail Flow Rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

Per aggiornare le regole esistenti per l'utilizzo delle nuove funzionalità OME:

1. Nell'interfaccia di amministrazione di Office 365, accedere a interfaccia di **amministrazione di _GT_ Exchange**.
2. Nell'interfaccia di amministrazione di Exchange, andare a **flusso di posta _GT_ Rules**.
3. Per ogni regola, **eseguire le operazioni seguenti**:
    - Selezionare **modifica la sicurezza dei messaggi**.
    - Selezionare **Apply Office 365 Message Encryption and Rights Protection**.
    - Selezionare un modello RMS dall'elenco.
    - Selezionare **Salva**.
    - Selezionare **OK**.
