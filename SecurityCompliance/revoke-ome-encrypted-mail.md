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
ms.openlocfilehash: 19eb874fa15a21c29a9eb2823829e81ff244a555
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011822"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="6c484-103">Revoca di posta elettronica la crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6c484-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="6c484-p101">In questo articolo fa parte di una serie di dimensioni maggiore di articoli su [Office 365 Message Encryption](ome.md). Revoca di posta elettronica attualmente, crittografate è in anteprima. Per continuare a migliorare la nostra offerta prevede che gli aggiornamenti e le modifiche per la caratteristica e il contenuto.</span><span class="sxs-lookup"><span data-stu-id="6c484-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="6c484-p102">Potrebbe essere necessario revocare un messaggio di posta elettronica che è stato già inviato. Se il messaggio di posta elettronica crittografato utilizzando la crittografia dei messaggi di Office 365 e si è un amministratore di Office 365, è possibile eseguire per la posta elettronica in determinate condizioni. In questo articolo viene descritto in quali circostanze ciò è possibile e su come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="6c484-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="6c484-110">Messaggi di posta elettronica crittografati che è possibile revocare</span><span class="sxs-lookup"><span data-stu-id="6c484-110">Encrypted emails that you can revoke</span></span>
<span data-ttu-id="6c484-p103">È possibile revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto un collegamento basate su marchio posta elettronica crittografati. Se il destinatario ha ricevuto un'esperienza in linea nativi in un client Outlook supportato, i messaggi di posta elettronica non possono essere revocati.</span><span class="sxs-lookup"><span data-stu-id="6c484-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="6c484-113">Se un destinatario riceve un'esperienza di collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e l'Account Microsoft destinatari (ad esempio, gli utenti outlook.com) ottenere un'esperienza in linea nel client di Outlook supportati.</span><span class="sxs-lookup"><span data-stu-id="6c484-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span>  
<span data-ttu-id="6c484-114">Tutti gli altri tipi di destinatario, ad esempio Gmail destinatari, ottenere un'esperienza di collegamento.</span><span class="sxs-lookup"><span data-stu-id="6c484-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span> 

<span data-ttu-id="6c484-p104">Disponibile a breve, le organizzazioni avranno la possibilità per forzare un'esperienza basata sul collegamento indipendentemente dall'identità del destinatario. In questo modo, tutti i destinatari verranno visualizzato un messaggio di posta elettronica personalizzato con un collegamento al portale di Office 365 Message Encryption dove sarà in grado di leggere e rispondere ai messaggi di posta elettronica crittografati. Ad esempio tramite posta elettronica crittografati sarà revocabile.</span><span class="sxs-lookup"><span data-stu-id="6c484-p104">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span> 
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="6c484-118">Esperienza dei destinatari per messaggi di posta elettronica crittografati revocati</span><span class="sxs-lookup"><span data-stu-id="6c484-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="6c484-119">Una volta che un messaggio di posta elettronica è stato revocato, il destinatario verrà visualizzato un errore durante il tentativo di accedere a posta elettronica crittografati tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".</span><span class="sxs-lookup"><span data-stu-id="6c484-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Schermata che mostra un revocati posta elettronica crittografati.](media/revoked-encrypted-email.png)
    
## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="6c484-121">Come revocare un messaggio di posta elettronica crittografato</span><span class="sxs-lookup"><span data-stu-id="6c484-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="6c484-p105">Passaggio 1. Ottenere l'ID del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6c484-p105">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="6c484-p106">È possibile revocare un messaggio crittografato è necessario raccogliere l'ID del messaggio di posta. L'ID messaggio è in genere nel formato:</span><span class="sxs-lookup"><span data-stu-id="6c484-p106">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="6c484-p107">Esistono diversi modi per trovare l'ID del messaggio di posta elettronica che si desidera revocare. In questa sezione vengono descritte due opzioni, ma è possibile utilizzare qualsiasi metodo che fornisce l'ID.</span><span class="sxs-lookup"><span data-stu-id="6c484-p107">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="6c484-128">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando traccia dei messaggi della protezione &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="6c484-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="6c484-129">Ricerca per la posta elettronica dal mittente o destinatario che utilizza un [Nuovo traccia dei messaggi in centro conformità e sicurezza di Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="6c484-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="6c484-p108">Dopo aver individuato il messaggio di posta elettronica selezionare per attivare il riquadro dei **dettagli di traccia dei messaggi** . Espandere **Più informazioni** per individuare il relativo ID.</span><span class="sxs-lookup"><span data-stu-id="6c484-p108">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

  #### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="6c484-132">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la crittografia dei messaggi di Office report in sicurezza &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="6c484-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>
1. <span data-ttu-id="6c484-133">In sicurezza &amp; centro conformità, accedere al **Rapporto di crittografia dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="6c484-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="6c484-134">Scegliere la tabella di **visualizzare i dettagli** e identificare il messaggio da revocare.</span><span class="sxs-lookup"><span data-stu-id="6c484-134">Choose the **View details** table and identify the message that you want to revoke.</span></span> 
3. <span data-ttu-id="6c484-135">Fare doppio clic sul messaggio per visualizzare i dettagli che includono il relativo ID.</span><span class="sxs-lookup"><span data-stu-id="6c484-135">Double-click the message to view details that include the Message ID.</span></span> 

### <a name="step-2-revoke-the-mail"></a><span data-ttu-id="6c484-p109">Passaggio 2. Revocare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6c484-p109">Step 2. Revoke the mail</span></span>  

<span data-ttu-id="6c484-138">Quando si conosce l'ID del messaggio di posta elettronica che si desidera revocare, è possibile revocare il messaggio di posta elettronica utilizzando il cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="6c484-138">Once you know the Message ID of the email you want to revoke, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span> 

1. <span data-ttu-id="6c484-139">[Connessione a Exchange Online tramite Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="6c484-139">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="6c484-140">Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c484-140">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>
    
    ```
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. <span data-ttu-id="6c484-141">Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c484-141">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>
    
    ```
    Get-OMEMessageStatus -MessageId "<messageId>"
    ```  
    <span data-ttu-id="6c484-142">Se revoca è stata eseguita correttamente, il cmdlet restituisce i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c484-142">If revocation was successful, the cmdlet returns the following result:</span></span>  

    ```The encrypted email with the subject "<subject>" and Message ID "<messageId>" was successfully revoked.```
