---
title: Revocare un messaggio di posta elettronica crittografato tramite Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: In qualità di amministratore di Office 365, è possibile revocare alcuni messaggi di posta elettronica crittografati con la crittografia dei messaggi di Office 365.
ms.openlocfilehash: 75b5e46e25f447ddac0de5a7911d0df8385da6b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214896"
---
# <a name="office-365-message-encryption-email-revocation"></a>Revoca della posta elettronica di crittografia messaggi di Office 365

Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md). In questo momento, la revoca della posta elettronica crittografata è in anteprima. Si prevede che gli aggiornamenti e le modifiche apportate alla funzionalità e al contenuto continuino a migliorare la nostra offerta.

È possibile che sia necessario revocare un messaggio di posta elettronica che è già stato inviato. Se il messaggio di posta elettronica è stato crittografato utilizzando la crittografia dei messaggi di Office 365 e si è un amministratore di Office 365, è possibile eseguire questa operazione per la posta elettronica in determinate condizioni. In questo articolo viene descritto in quali circostanze è possibile e come procedere.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Messaggi di posta elettronica crittografati che è possibile revocare

È possibile revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto una e-mail crittografata basata sul collegamento. Se il destinatario ha ricevuto un'esperienza nativa in linea in un client di Outlook supportato, tali messaggi di posta elettronica non possono essere revocati.

Se un destinatario riceve un'esperienza basata sul collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e destinatari dell'account Microsoft (ad esempio, gli utenti di outlook.com) ricevono un'esperienza in linea nei client Outlook supportati. Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail, ricevono un'esperienza basata sul collegamento.

In breve, le organizzazioni avranno la possibilità di forzare un'esperienza basata sul collegamento indipendentemente dall'identità del destinatario. In questo modo, tutti i destinatari riceveranno un messaggio di posta elettronica di marca con un collegamento al portale di crittografia dei messaggi di Office 365, dove potranno leggere e rispondere ai messaggi di posta elettronica crittografati. Tutti tali messaggi di posta elettronica crittografati saranno revocabili.
  
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

Per verificare se è possibile revocare o meno un determinato messaggio di posta elettronica, eseguire la procedura seguente.

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEMessageStatus come indicato di seguito:
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   Restituisce l'oggetto del messaggio e indica se il messaggio è revocabile. Per esempio

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>Passaggio 3. Revocare la posta elettronica  

Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare la posta elettronica utilizzando il cmdlet Set-OMEMessageRevocation.

1. [Connettersi a Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:  

    `Revoked: True`
