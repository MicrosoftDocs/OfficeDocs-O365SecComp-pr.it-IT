---
title: Revocare il messaggio di posta elettronica crittografato per la crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Amministratore di Office 365, è possibile revocare alcuni messaggi di posta elettronica crittografati con Office 365 Message Encryption.
ms.openlocfilehash: b2fd3e07bec6dfedd783a8a68169fc5f990a80d3
ms.sourcegitcommit: 2150f49cf4305b75591a238ff649c57684c7632f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004249"
---
# <a name="office-365-message-encryption-email-revocation"></a>Revoca di posta elettronica la crittografia dei messaggi di Office 365

In questo articolo fa parte di una serie di dimensioni maggiore di articoli su [Office 365 Message Encryption](ome.md). Revoca di posta elettronica attualmente, crittografate è in anteprima. Per continuare a migliorare la nostra offerta prevede che gli aggiornamenti e le modifiche per la caratteristica e il contenuto.

Potrebbe essere necessario revocare un messaggio di posta elettronica che è stato già inviato. Se il messaggio di posta elettronica crittografato utilizzando la crittografia dei messaggi di Office 365 e si è un amministratore di Office 365, è possibile eseguire per la posta elettronica in determinate condizioni. In questo articolo viene descritto in quali circostanze ciò è possibile e su come eseguire questa operazione.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Messaggi di posta elettronica crittografati che è possibile revocare
È possibile revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto un collegamento basate su marchio posta elettronica crittografati. Se il destinatario ha ricevuto un'esperienza in linea nativi in un client Outlook supportato, i messaggi di posta elettronica non possono essere revocati.

Se un destinatario riceve un'esperienza di collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e l'Account Microsoft destinatari (ad esempio, gli utenti outlook.com) ottenere un'esperienza in linea nel client di Outlook supportati.  
Tutti gli altri tipi di destinatario, ad esempio Gmail destinatari, ottenere un'esperienza di collegamento. 

Disponibile a breve, le organizzazioni avranno la possibilità per forzare un'esperienza basata sul collegamento indipendentemente dall'identità del destinatario. In questo modo, tutti i destinatari verranno visualizzato un messaggio di posta elettronica personalizzato con un collegamento al portale di Office 365 Message Encryption dove sarà in grado di leggere e rispondere ai messaggi di posta elettronica crittografati. Ad esempio tramite posta elettronica crittografati sarà revocabile. 
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Esperienza dei destinatari per messaggi di posta elettronica crittografati revocati

Una volta che un messaggio di posta elettronica è stato revocato, il destinatario verrà visualizzato un errore durante il tentativo di accedere a posta elettronica crittografati tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".

![Schermata che mostra un revocati posta elettronica crittografati.](media/revoked-encrypted-email.png)
    
## <a name="how-to-revoke-an-encrypted-email"></a>Come revocare un messaggio di posta elettronica crittografato

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Passaggio 1. Ottenere l'ID del messaggio di posta elettronica

È possibile revocare un messaggio crittografato è necessario raccogliere l'ID del messaggio di posta. L'ID messaggio è in genere nel formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Esistono diversi modi per trovare l'ID del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte due opzioni, ma è possibile utilizzare qualsiasi metodo che fornisce l'ID.

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando traccia dei messaggi della protezione &amp; centro conformità

1. Ricerca per la posta elettronica dal mittente o destinatario che utilizza un [Nuovo traccia dei messaggi in centro conformità e sicurezza di Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).
2. Dopo aver individuato il messaggio di posta elettronica selezionare per attivare il riquadro dei **dettagli di traccia dei messaggi** . Espandere **Più informazioni** per individuare il relativo ID.

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la crittografia dei messaggi di Office report in sicurezza &amp; centro conformità
1. In sicurezza &amp; centro conformità, accedere al **Rapporto di crittografia dei messaggi**.
2. Scegliere la tabella di **visualizzare i dettagli** e identificare il messaggio da revocare. 
3. Fare doppio clic sul messaggio per visualizzare i dettagli che includono il relativo ID. 

### <a name="step-2-revoke-the-mail"></a>Passaggio 2. Revocare la posta elettronica  

Quando si conosce l'ID del messaggio di posta elettronica che si desidera revocare, è possibile revocare il messaggio di posta elettronica utilizzando il cmdlet Set-OMEMessageRevocation. 

1. [Connessione a Exchange Online tramite Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).
    
2. Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:
    
    ```
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:
    
    ```
    Get-OMEMessageStatus -MessageId "<messageId>"
    ```  
    Se revoca è stata eseguita correttamente, il cmdlet restituisce i risultati seguenti:  

    ```The encrypted email with the subject "<subject>" and Message ID "<messageId>" was successfully revoked.```
