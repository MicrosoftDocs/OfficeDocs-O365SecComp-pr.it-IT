---
title: Nuovo criterio di crittografia dei messaggi di Office 365 per le informazioni riservate
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Applicato automaticamente il criterio di Office 365 Message Encryption per la distribuzione ai tenant tutti i tipi di informazioni riservate.'
ms.openlocfilehash: f5996707d1cafe8dc1bf90856878de0a4fb7b77b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "27752088"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="2b260-103">Criteri di crittografia dei messaggi di Office 365 per le informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="2b260-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="2b260-p101">In Office 365 tenant che verrà applicata la crittografia dei messaggi di Office 365 per tutti i messaggi di posta elettronica che contengono informazioni riservate e che vengono inviate all'esterno dell'organizzazione che verrà creata un nuovo criterio automatico. Questa nuova regola di flusso di posta elettronica di Exchange verrà creata automaticamente nel tenant Office 365 in modo che l'organizzazione verrà protetti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2b260-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="when-to-expect-the-update-for-your-tenant"></a><span data-ttu-id="2b260-106">Momento in cui si prevede che l'aggiornamento per il tenant</span><span class="sxs-lookup"><span data-stu-id="2b260-106">When to expect the update for your tenant</span></span>

<span data-ttu-id="2b260-p102">L'organizzazione riceverà una notifica nel centro di messaggi Office 365 notifica che indica la data in cui verrà creato il criterio automatico nel tenant. Sono disponibili almeno un avviso di 30 giorni e che sia anche l'opzione per non ricevere messaggi. Uno scenario in cui si desidera potenzialmente esplicito è se si dispone di una soluzione di prevenzione della perdita di dati 3rd parti che già analizza per i tipi di riservati. Ulteriori informazioni su come escludere sono disponibili più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2b260-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types. More details on how to opt-out are available later in this article.</span></span>

## <a name="sensitive-information-type-policy-details"></a><span data-ttu-id="2b260-110">Dettagli dei criteri tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="2b260-110">Sensitive information type policy details</span></span>

<span data-ttu-id="2b260-111">Verrà creata una regola di flusso di posta di Exchange nell'organizzazione che verrà automaticamente crittografare i messaggi di posta elettronica di fuori dell'organizzazione con il *Solo crittografa* criteri che contengono i tipi di informazioni riservate seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b260-111">An Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if they contain the following sensitive information types:</span></span>

- <span data-ttu-id="2b260-112">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="2b260-112">ABA routing number</span></span>
- <span data-ttu-id="2b260-113">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="2b260-113">Credit card Number</span></span>
- <span data-ttu-id="2b260-114">Numero di Drug imposizione Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="2b260-114">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="2b260-p103">Usa / numero di passaporto Regno Unito</span><span class="sxs-lookup"><span data-stu-id="2b260-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="2b260-117">Numero di conto bancario negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="2b260-117">U.S. bank account number</span></span>
- <span data-ttu-id="2b260-118">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="2b260-118">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="2b260-119">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="2b260-119">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="2b260-120">I tipi di sensibili esatti possono variare dalle impostazioni locali dell'organizzazione e vengono comunicati nella notifica centro messaggi.</span><span class="sxs-lookup"><span data-stu-id="2b260-120">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="2b260-121">Che cosa è necessario eseguire per preparare la modifica</span><span class="sxs-lookup"><span data-stu-id="2b260-121">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="2b260-p104">Non è necessario aggiornare o modificare le impostazioni di configurazione di Office 365 esistente prima di questa modifica nuova. Tuttavia, si desidera aggiornare qualsiasi documentazione applicabile per l'utente finale e materiale di formazione per preparare gli utenti dell'organizzazione per la modifica. Condividere le risorse di Office 365 Message Encryption con gli utenti nel modo appropriato:</span><span class="sxs-lookup"><span data-stu-id="2b260-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="2b260-125">Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC</span><span class="sxs-lookup"><span data-stu-id="2b260-125">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="2b260-126">Office 365 Essentials Video: Crittografia dei messaggi Office</span><span class="sxs-lookup"><span data-stu-id="2b260-126">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="2b260-127">Questa modifica rappresentare nel Registro di controllo?</span><span class="sxs-lookup"><span data-stu-id="2b260-127">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="2b260-p105">Questa attività è possibile controllare ed è disponibile per i clienti.  L'operazione è 'New-TransportRule' e un frammento di una voce di controllo di esempio di ricerca del Registro di controllo nel centro conformità e sicurezza è seguito:</span><span class="sxs-lookup"><span data-stu-id="2b260-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="2b260-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey specificato": "Microsoft operatore"," UserType": 3,"Version": 1,"carico di lavoro":"Di Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"UserId "," ":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX ( 15.20.1382.008)","Parameters": {"Nome":"Organizzazione","Il valore":" g 123456 221-12346"{"Nome":"ApplyRightsProtectionTemplate","Il valore":"Crittografa"}, {"Nome":"Name","Il valore":"Crittografare pubblicità riservati in uscita (da regola casella)"}, {"Nome":" MessageContainsDataClassifications"... e così via.*</span><span class="sxs-lookup"><span data-stu-id="2b260-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="2b260-131">Come escludere?</span><span class="sxs-lookup"><span data-stu-id="2b260-131">How do I opt-out?</span></span>

<span data-ttu-id="2b260-132">Se si desidera dissociare modifica, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2b260-132">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="2b260-p106">Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="2b260-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>
2. <span data-ttu-id="2b260-135">Eseguire il cmdlet Set-IRMConfiguration come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2b260-135">Run the Set-IRMConfiguration cmdlet as follows:</span></span>

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-the-automatic-policy"></a><span data-ttu-id="2b260-136">Come è possibile disattivare il criterio automatico?</span><span class="sxs-lookup"><span data-stu-id="2b260-136">How do I disable the automatic policy?</span></span>

<span data-ttu-id="2b260-137">Se non escludere modifica e la regola di posta elettronica di Exchange sia stata già creata, è possibile [disabilitare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) passando a **flusso di posta** > **regole** in Exchange admin center (EAC) e disabilitare la regola "*Crittografa in uscita messaggi di posta elettronica riservati (fuori regola casella)*".</span><span class="sxs-lookup"><span data-stu-id="2b260-137">If you didn’t opt-out of this change and the Exchange mail rule has already been created, you can [disable the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
