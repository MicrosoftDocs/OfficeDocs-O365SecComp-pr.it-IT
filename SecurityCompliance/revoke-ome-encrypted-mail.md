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
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="a4fd7-103">Revoca della posta elettronica di crittografia messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="a4fd7-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="a4fd7-p101">Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md). In questo momento, la revoca della posta elettronica crittografata è in anteprima. Si prevede che gli aggiornamenti e le modifiche apportate alla funzionalità e al contenuto continuino a migliorare la nostra offerta.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="a4fd7-p102">È possibile che sia necessario revocare un messaggio di posta elettronica che è già stato inviato. Se il messaggio di posta elettronica è stato crittografato utilizzando la crittografia dei messaggi di Office 365 e si è un amministratore di Office 365, è possibile eseguire questa operazione per la posta elettronica in determinate condizioni. In questo articolo viene descritto in quali circostanze è possibile e come procedere.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="a4fd7-110">Messaggi di posta elettronica crittografati che è possibile revocare</span><span class="sxs-lookup"><span data-stu-id="a4fd7-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="a4fd7-p103">È possibile revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto una e-mail crittografata basata sul collegamento. Se il destinatario ha ricevuto un'esperienza nativa in linea in un client di Outlook supportato, tali messaggi di posta elettronica non possono essere revocati.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="a4fd7-p104">Se un destinatario riceve un'esperienza basata sul collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e destinatari dell'account Microsoft (ad esempio, gli utenti di outlook.com) ricevono un'esperienza in linea nei client Outlook supportati. Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail, ricevono un'esperienza basata sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p104">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients. All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

<span data-ttu-id="a4fd7-p105">In breve, le organizzazioni avranno la possibilità di forzare un'esperienza basata sul collegamento indipendentemente dall'identità del destinatario. In questo modo, tutti i destinatari riceveranno un messaggio di posta elettronica di marca con un collegamento al portale di crittografia dei messaggi di Office 365, dove potranno leggere e rispondere ai messaggi di posta elettronica crittografati. Tutti tali messaggi di posta elettronica crittografati saranno revocabili.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p105">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span>
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="a4fd7-118">Esperienza dei destinatari per i messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="a4fd7-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="a4fd7-119">Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceverà un errore durante il tentativo di accedere alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".</span><span class="sxs-lookup"><span data-stu-id="a4fd7-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Schermata che visualizza un messaggio di posta elettronica crittografato revocato.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="a4fd7-121">Come revocare un messaggio di posta elettronica crittografato</span><span class="sxs-lookup"><span data-stu-id="a4fd7-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="a4fd7-p106">Passaggio 1. Ottenere l'ID del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p106">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="a4fd7-p107">Prima di revocare una posta crittografata, è necessario raccogliere l'ID del messaggio di posta elettronica. Il MessageId è in genere del formato seguente:</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p107">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="a4fd7-p108">Sono disponibili diversi modi per individuare l'ID del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte alcune opzioni, ma è possibile utilizzare qualsiasi metodo che fornisca l'ID.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p108">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="a4fd7-128">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la traccia dei messaggi nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a4fd7-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="a4fd7-129">Cercare il messaggio di posta elettronica in base al mittente o al destinatario utilizzando la [nuova traccia dei messaggi in Office 365 Security _AMP_ Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="a4fd7-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="a4fd7-p109">Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **Dettagli traccia dei messaggi** . Espandere **ulteriori informazioni** per individuare l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p109">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="a4fd7-132">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando i rapporti di crittografia dei messaggi di &amp; Office nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a4fd7-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="a4fd7-133">Nel centro sicurezza &amp; e conformità, passare al **rapporto di crittografia dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="a4fd7-134">Scegliere la tabella **Visualizza dettagli** e identificare il messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-134">Choose the **View details** table and identify the message that you want to revoke.</span></span>
3. <span data-ttu-id="a4fd7-135">Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-135">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="a4fd7-p110">Passaggio 2. Verificare che la posta sia revocabile</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p110">Step 2. Verify that the mail is revocable</span></span>

<span data-ttu-id="a4fd7-138">Per verificare se è possibile revocare o meno un determinato messaggio di posta elettronica, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-138">To verify whether or not you can revoke a particular email message, complete these steps.</span></span>

1. <span data-ttu-id="a4fd7-p111">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="a4fd7-141">Eseguire il cmdlet Set-OMEMessageStatus come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a4fd7-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="a4fd7-p112">Restituisce l'oggetto del messaggio e indica se il messaggio è revocabile. Per esempio</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p112">This returns the subject of the message and whether the message is revocable. For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="a4fd7-p113">Passaggio 3. Revocare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a4fd7-p113">Step 3. Revoke the mail</span></span>  

<span data-ttu-id="a4fd7-146">Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare la posta elettronica utilizzando il cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="a4fd7-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="a4fd7-147">[Connettersi a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="a4fd7-147">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="a4fd7-148">Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a4fd7-148">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="a4fd7-149">Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a4fd7-149">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    <span data-ttu-id="a4fd7-150">Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="a4fd7-150">If revocation was successful, the cmdlet returns the following result:</span></span>  

    `Revoked: True`
