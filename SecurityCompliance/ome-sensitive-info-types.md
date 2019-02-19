---
title: Criteri di crittografia dei messaggi di Office 365 per informazioni riservate
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: i criteri di crittografia dei messaggi di Office 365 per i tipi di informazioni riservate sono ora disponibili.'
ms.openlocfilehash: e2a72ee85ca65a2fe8ae1543979b51915ff0a88f
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696200"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="70240-103">Criteri di crittografia dei messaggi di Office 365 per informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="70240-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="70240-p101">Update (1/30/19): nell'ottobre 2018 abbiamo lavorato con un piccolo campione di clienti per capire se è possibile semplificare la protezione tramite la crittografia automatica dei messaggi di posta elettronica sensibili in base a determinati tipi di informazioni riservate. In base al feedback positivo di questo esempio, si è deciso di espandersi a un profilo più vario dei tenant nel dicembre 2018. Dopo aver comunicato il prossimo roll-out per selezionare i tenant, abbiamo ascoltato i commenti e abbiamo determinato che i clienti con ambienti più complessi volevano implementare le regole con maggiore cautela e quindi adeguare i piani.</span><span class="sxs-lookup"><span data-stu-id="70240-p101">Update (1/30/19): In October 2018, we worked with a small sample of customers to understand if we can simplify protection by automatically encrypting sensitive emails based on certain sensitive information types. Based on positive feedback from this sample, we decided to expand to a more diverse profile of tenants in December 2018. After communicating the next roll-out to select tenants, we listened to your feedback and determined that customers with more complex environments wanted to implement the rules more cautiously, and we are therefore adjusting our plans.</span></span>

<span data-ttu-id="70240-p102">Se l'organizzazione è stata selezionata per il roll-out a partire dal 15 gennaio 2019, non verrà eliminato il criterio automatico. Al contrario, vengono fornite istruzioni in questo articolo su come è possibile completare l'implementazione. Continuare a leggere per scoprire come.</span><span class="sxs-lookup"><span data-stu-id="70240-p102">If your organization was selected for the roll-out starting January 15, 2019, we will not roll out the automatic policy. Instead, we are providing instructions in this article on how you can complete the roll-out yourselves. Keep reading to find out how.</span></span>

||
|:-----|
|<span data-ttu-id="70240-p103">Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="70240-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a><span data-ttu-id="70240-113">Come creare il criterio tipo di informazioni riservate per il tenant</span><span class="sxs-lookup"><span data-stu-id="70240-113">How to create the sensitive information type policy for your tenant</span></span>

<span data-ttu-id="70240-p104">È possibile utilizzare le regole del flusso di posta di Exchange o la prevenzione della perdita di dati (DLP) di Office 365 per creare i criteri dei tipi di informazioni riservate. Per creare una regola del flusso di posta di Exchange, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70240-p104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create the sensitive information type policy. To create an Exchange mail flow rule you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="70240-116">Per creare il criterio mediante le regole del flusso di posta nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="70240-116">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="70240-p105">Accedere all'interfaccia di amministrazione di Exchange (EAC) e passare a**regole**del **flusso** > di posta. Creare una regola che applica la crittografia dei messaggi di Office 365 in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.</span><span class="sxs-lookup"><span data-stu-id="70240-p105">Sign-in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**. There, create a rule that applies Office 365 Message Encryption based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="70240-119">Per creare il criterio mediante le regole del flusso di posta in PowerShell</span><span class="sxs-lookup"><span data-stu-id="70240-119">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="70240-p106">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Utilizzare i cmdlet Set-IRMConfiguration e New-TransporRule per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="70240-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Use the Set-IRMConfiguration and New-TransporRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="70240-123">Esempio di regola del flusso di posta creato con PowerShell</span><span class="sxs-lookup"><span data-stu-id="70240-123">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="70240-124">L'esecuzione dei comandi seguenti in PowerShell consente di creare una regola del flusso di posta di Exchange che consente di crittografare automaticamente i messaggi esterni all'organizzazione con il criterio di *sola crittografia* se i messaggi di posta elettronica o i relativi allegati contengono i seguenti elementi sensibili tipi di informazioni:</span><span class="sxs-lookup"><span data-stu-id="70240-124">Running the following commands in PowerShell create an Exchange mail flow rule that automatically encrypts emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="70240-125">Numero di Routing ABA</span><span class="sxs-lookup"><span data-stu-id="70240-125">ABA routing number</span></span>
- <span data-ttu-id="70240-126">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="70240-126">Credit card Number</span></span>
- <span data-ttu-id="70240-127">Numero dell'agenzia di applicazione della droga (DEA)</span><span class="sxs-lookup"><span data-stu-id="70240-127">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="70240-p107">Numero di passaporto Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="70240-p107">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="70240-130">Numero di conto corrente bancario degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="70240-130">U.S. bank account number</span></span>
- <span data-ttu-id="70240-131">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="70240-131">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="70240-132">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="70240-132">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="70240-133">Modalità di accesso degli allegati ai destinatari</span><span class="sxs-lookup"><span data-stu-id="70240-133">How recipients access attachments</span></span>

<span data-ttu-id="70240-134">Dopo che un messaggio è stato crittografato, i destinatari avranno accesso illimitato agli allegati una volta che accedono e aprono la posta elettronica crittografata.</span><span class="sxs-lookup"><span data-stu-id="70240-134">Once a message is encrypted, recipients will have unrestricted access to attachments once they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="70240-135">Per preparare questa modifica</span><span class="sxs-lookup"><span data-stu-id="70240-135">To prepare for this change</span></span>

<span data-ttu-id="70240-p108">Potrebbe essere necessario aggiornare la documentazione per gli utenti finali applicabile e i materiali di formazione per preparare le persone all'interno dell'organizzazione per questa modifica. Condividere queste risorse di crittografia dei messaggi di Office 365 con gli utenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="70240-p108">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="70240-138">Inviare, visualizzare e rispondere a messaggi crittografati in Outlook per PC</span><span class="sxs-lookup"><span data-stu-id="70240-138">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="70240-139">Video di Office 365 Essentials: crittografia dei messaggi di Office</span><span class="sxs-lookup"><span data-stu-id="70240-139">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="70240-140">Visualizzare queste modifiche nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="70240-140">View these changes in the Audit log</span></span>

<span data-ttu-id="70240-p109">Questa attività è controllata ed è disponibile per gli amministratori di Office 365. L'operazione è' New-TransportRule ' e un frammento di una voce di controllo di esempio dalla ricerca del registro di controllo nel centro sicurezza & Compliance è riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="70240-p109">This activity is audited and is available to Office 365 administrators. The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="70240-143">*{"CreationTime": "2018-11-28T23:35:01", "ID": "A1b2C3d4-DAA0-4c4f-A019-03a1234a1b0c", "Operation": "New-TransportRule", "IDOrganizzazione": "123456-221D-12345", "RecordType": 1, "ResultStatus": "true", "UserKey": "Microsoft operator", " UserType ": 3," Version ": 1," carico di lavoro ":" Exchange "," ClientIP ":" 123.456.147.68:17584 "," ObjectId ":" "," UserId ":" Microsoft operator","ExternalAccess":true,"OrganizationName":"contoso. onmicrosoft. com "," OriginatingServer ":" CY4PR13MBXXXX ( 15.20.1382.008) "," parametri ": {" nome ":" organizzazione "," valore ":" 123456-221D-12346 "{" Name ":" ApplyRightsProtectionTemplate consente "," value ":" Encrypt "}, {" Name ":" Name "," value ":" Encrypt Outbound emails sensitive (out of box Rule) "}, {" Name ":" MessageContainsDataClassifications "... ecc.*</span><span class="sxs-lookup"><span data-stu-id="70240-143">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span> |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="70240-144">Per disabilitare o personalizzare i criteri dei tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="70240-144">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="70240-145">Dopo aver creato la regola del flusso di posta di Exchange, è possibile [disabilitare o modificare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) accedendo alle**regole** del **flusso** > di posta nell'interfaccia di amministrazione di Exchange (EAC) e disabilitando la regola "crittografare i*messaggi di posta elettronica sensibili in uscita (regola fuori dalla casella)* ".</span><span class="sxs-lookup"><span data-stu-id="70240-145">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
