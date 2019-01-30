---
title: Nuovo criterio di crittografia dei messaggi di Office 365 per le informazioni riservate
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/16/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Applicato automaticamente il criterio di Office 365 Message Encryption per la distribuzione ai tenant tutti i tipi di informazioni riservate.'
ms.openlocfilehash: f83bf0fe572586b3becf2dd53395e611bdaaea24
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614380"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="11654-103">Criteri di crittografia dei messaggi di Office 365 per le informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="11654-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="11654-p101">Per un gruppo selezionato di tenant, in base alle dimensioni dell'organizzazione e la complessità del flusso di posta, ciò un lente introduzione di nuovi criteri automatici in Office 365 tenant che verrà applicata la crittografia dei messaggi di Office 365 per i messaggi di posta elettronica che contengono determinati tipi di riservati informazioni. Sottoposti a test seguente con un piccolo gruppo di tenant. Questo criterio non inizierà a tutte le organizzazioni e considerazioni, ad esempio dimensioni dell'organizzazione e la complessità del flusso di posta verrà utilizzata per determinare l'idoneità per questo (in inglese) in uscita. Se l'organizzazione è selezionato per questo (in inglese) in uscita, si riceverà una notifica nel centro di messaggi Office 365 notifica che indica la data in cui verrà creato il criterio automatico e sono disponibili almeno un avviso di 30 giorni e l'opzione per non ricevere messaggi. Se non si desidera attendere Microsoft creare questo criterio e si desidera effettuare questa operazione se stessi, è possibile creare questo criterio automatico utilizzando le regole di flusso di posta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="11654-p101">For a select group of tenants, based on their organization size and complexity of mail flow, we are doing a slow roll-out of a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to emails that contain certain types of sensitive information. We are testing this with a small group of tenants. This policy will not be rolled out to all organizations and considerations such as organization size and complexity of mail flow will be used to determine the eligibility for this roll-out. If your organization is selected for this roll-out, you will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created and you will be given at least a 30-day notice and the option to opt-out. If you don't want to wait for Microsoft to create this policy and would like to do so yourselves, you can create this automatic policy using Exchange Mail Flow rules.</span></span>

## <a name="when-to-expect-the-update-for-your-tenant"></a><span data-ttu-id="11654-107">Momento in cui si prevede che l'aggiornamento per il tenant</span><span class="sxs-lookup"><span data-stu-id="11654-107">When to expect the update for your tenant</span></span>

<span data-ttu-id="11654-p102">L'organizzazione riceverà una notifica nel centro di messaggi Office 365 notifica che indica la data in cui verrà creato il criterio automatico nel tenant. Sono disponibili almeno un avviso di 30 giorni e che sia anche l'opzione per non ricevere messaggi. Uno scenario in cui si desidera potenzialmente esplicito è se si dispone di una soluzione di prevenzione della perdita di dati 3rd parti che già analizza per i tipi di riservati. Ulteriori informazioni su come escludere sono disponibili più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="11654-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types. More details on how to opt-out are available later in this article.</span></span>

## <a name="sensitive-information-type-policy-details"></a><span data-ttu-id="11654-111">Dettagli dei criteri tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="11654-111">Sensitive information type policy details</span></span>

<span data-ttu-id="11654-112">Verrà creata una regola di flusso di posta di Exchange nell'organizzazione che verrà automaticamente crittografare i messaggi di posta elettronica di fuori dell'organizzazione con il *Solo crittografa* criteri se i messaggi di posta elettronica o gli allegati sono i seguenti tipi di informazioni riservate:</span><span class="sxs-lookup"><span data-stu-id="11654-112">An Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="11654-113">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="11654-113">ABA routing number</span></span>
- <span data-ttu-id="11654-114">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="11654-114">Credit card Number</span></span>
- <span data-ttu-id="11654-115">Numero di Drug imposizione Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="11654-115">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="11654-p103">Usa / numero di passaporto Regno Unito</span><span class="sxs-lookup"><span data-stu-id="11654-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="11654-118">Numero di conto bancario negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="11654-118">U.S. bank account number</span></span>
- <span data-ttu-id="11654-119">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="11654-119">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="11654-120">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="11654-120">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="11654-121">I tipi di sensibili esatti possono variare dalle impostazioni locali dell'organizzazione e vengono comunicati nella notifica centro messaggi.</span><span class="sxs-lookup"><span data-stu-id="11654-121">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="11654-122">Che cosa è necessario eseguire per preparare la modifica</span><span class="sxs-lookup"><span data-stu-id="11654-122">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="11654-p104">Non è necessario aggiornare o modificare le impostazioni di configurazione di Office 365 esistente prima di questa modifica nuova. Tuttavia, si desidera aggiornare qualsiasi documentazione applicabile per l'utente finale e materiale di formazione per preparare gli utenti dell'organizzazione per la modifica. Condividere le risorse di Office 365 Message Encryption con gli utenti nel modo appropriato:</span><span class="sxs-lookup"><span data-stu-id="11654-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="11654-126">Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC</span><span class="sxs-lookup"><span data-stu-id="11654-126">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="11654-127">Office 365 Essentials Video: Crittografia dei messaggi Office</span><span class="sxs-lookup"><span data-stu-id="11654-127">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="11654-128">Questa modifica rappresentare nel Registro di controllo?</span><span class="sxs-lookup"><span data-stu-id="11654-128">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="11654-p105">Questa attività è possibile controllare ed è disponibile per i clienti.  L'operazione è 'New-TransportRule' e un frammento di una voce di controllo di esempio di ricerca del Registro di controllo di sicurezza & centro conformità è seguito:</span><span class="sxs-lookup"><span data-stu-id="11654-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="11654-131">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey specificato": "Microsoft operatore"," UserType": 3,"Version": 1,"carico di lavoro":"Di Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"UserId "," ":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX ( 15.20.1382.008)","Parameters": {"Nome":"Organizzazione","Il valore":" g 123456 221-12346"{"Nome":"ApplyRightsProtectionTemplate","Il valore":"Crittografa"}, {"Nome":"Name","Il valore":"Crittografare pubblicità riservati in uscita (da regola casella)"}, {"Nome":" MessageContainsDataClassifications"... e così via.*</span><span class="sxs-lookup"><span data-stu-id="11654-131">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="11654-132">Come escludere?</span><span class="sxs-lookup"><span data-stu-id="11654-132">How do I opt-out?</span></span>

<span data-ttu-id="11654-133">Se si desidera dissociare modifica, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="11654-133">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="11654-p106">Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="11654-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>
2. <span data-ttu-id="11654-136">Eseguire il cmdlet Set-IRMConfiguration come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="11654-136">Run the Set-IRMConfiguration cmdlet as follows:</span></span>

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-or-customize-the-automatic-policy"></a><span data-ttu-id="11654-137">Come disabilitare o personalizzare il criterio automatico?</span><span class="sxs-lookup"><span data-stu-id="11654-137">How do I disable or customize the automatic policy?</span></span>

<span data-ttu-id="11654-138">Se non escludere modifica e la regola di flusso di posta di Exchange sia stata già creata, è possibile [disattivare o modificare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) passando a **flusso di posta** > **regole** in Exchange admin center (EAC) e disabilitare la regola "*Crittografa in uscita tramite posta elettronica riservati (fuori regola casella)*".</span><span class="sxs-lookup"><span data-stu-id="11654-138">If you didn’t opt-out of this change and the Exchange mail flow rule has already been created, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
