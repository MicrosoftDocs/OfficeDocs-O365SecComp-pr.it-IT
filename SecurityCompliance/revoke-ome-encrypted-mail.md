---
title: Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: In qualità di amministratore di Office 365, è possibile revocare alcuni messaggi di posta elettronica crittografati con la crittografia avanzata dei messaggi di Office 365.
ms.openlocfilehash: 098ce50791152c8bbb4e4692d6fb85e4c2c7cb58
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156788"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption

La revoca del messaggio di posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365. La crittografia avanzata dei messaggi di Office 365 è disponibile nella parte superiore della crittografia messaggi di Office 365 in alcuni abbonamenti. La crittografia avanzata dei messaggi è inclusa in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 e Office 365 Education a5. Se nell'organizzazione è presente un abbonamento a Office 365 che non include la crittografia avanzata dei messaggi di Office 365, è possibile acquistare la crittografia avanzata del messaggio come componente aggiuntivo con la conformità E5 della SKU per la conformità avanzata.

Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md).

È possibile che sia necessario revocare un messaggio di posta elettronica che è già stato inviato. Se il messaggio di posta elettronica è stato crittografato utilizzando la crittografia avanzata dei messaggi di Office 365 e si è un amministratore di Office 365, è possibile eseguire questa operazione per la posta elettronica in determinate condizioni. In questo articolo viene descritto in quali circostanze è possibile e come procedere.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Messaggi di posta elettronica crittografati che è possibile revocare

È possibile revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto una e-mail crittografata basata sul collegamento. Se il destinatario ha ricevuto un'esperienza nativa in linea in un client di Outlook supportato, tali messaggi di posta elettronica non possono essere revocati.

Se un destinatario riceve un'esperienza basata sul collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e destinatari dell'account Microsoft (ad esempio, gli utenti di outlook.com) ricevono un'esperienza in linea nei client Outlook supportati. Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail, ricevono un'esperienza basata sul collegamento.

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Esperienza dei destinatari per i messaggi di posta elettronica crittografati

Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceverà un errore durante il tentativo di accedere alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".

![Schermata che visualizza un messaggio di posta elettronica crittografato revocato.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>Come revocare un messaggio di posta elettronica crittografato

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Passaggio 1. Ottenere l'ID del messaggio di posta elettronica

Prima di revocare una posta crittografata, è necessario raccogliere l'ID del messaggio di posta elettronica. Il MessageId è in genere del formato seguente:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Sono disponibili diversi modi per individuare l'ID del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte alcune opzioni, ma è possibile utilizzare qualsiasi metodo che fornisca l'ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la traccia dei messaggi nel &amp; Centro sicurezza e conformità

1. Cercare il messaggio di posta elettronica in base al mittente o al destinatario utilizzando la [nuova traccia dei messaggi in Office 365 Security _AMP_ Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **Dettagli traccia dei messaggi** . Espandere **ulteriori informazioni** per individuare l'ID del messaggio.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando i rapporti di crittografia dei messaggi di &amp; Office nel centro sicurezza e conformità

1. Nel centro sicurezza &amp; e conformità, passare al **rapporto di crittografia dei messaggi**.

2. Scegliere la tabella **Visualizza dettagli** e identificare il messaggio che si desidera revocare.

3. Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID del messaggio.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Passaggio 2. Verificare che la posta sia revocabile

Per verificare se è possibile revocare un determinato messaggio di posta elettronica, verificare se il campo stato revoca è visibile nella **** tabella Details del &amp; Centro sicurezza e conformità.

Per verificare se è possibile revocare o meno un messaggio di posta elettronica specifico utilizzando Windows PowerShell, eseguire la procedura seguente.

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEMessageStatus come indicato di seguito:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Restituisce l'oggetto del messaggio e indica se il messaggio è revocabile. For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>Passaggio 3. Revocare la posta elettronica  

Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare la posta elettronica.

Per revocare il messaggio di posta elettronica &amp; nel centro sicurezza e conformità, fare clic su **revoca**nella tabella details. ****

È possibile revocare un messaggio di posta elettronica utilizzando Windows PowerShell utilizzando il cmdlet Set-OMEMessageRevocation.

1. [Connettersi a PowerShell per Exchange Online](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Crittografia messaggi avanzata di Office 365-scadenza del messaggio di posta elettronica](ome-advanced-expiration.md)

- [Descrizione del servizio criteri di conformità e del messaggio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)