---
title: Nuovo criterio di crittografia dei messaggi di Office 365 per le informazioni riservate
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Nuovo Office 365 Message Encryption criterio per le informazioni riservate.'
ms.openlocfilehash: 180050d1bf9303f6d29bc126e66ac53211c2fb34
ms.sourcegitcommit: 3aae959ea1ac5ef61a9942c681d334831e6b6038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271092"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="87475-103">Nuovo criterio di crittografia dei messaggi di Office 365 per le informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="87475-103">New Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="87475-p101">In Office 365 tenant che verrà applicata la crittografia dei messaggi di Office 365 per tutti i messaggi di posta elettronica che contengono informazioni riservate e che vengono inviate all'esterno dell'organizzazione che verrà creata un nuovo criterio automatico. Questa nuova regola di flusso di posta elettronica di Exchange verrà creata automaticamente nel tenant Office 365 in modo che l'organizzazione verrà protetti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="87475-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="how-will-this-work"></a><span data-ttu-id="87475-106">Come verrà questo tipo di lavoro?</span><span class="sxs-lookup"><span data-stu-id="87475-106">How will this work?</span></span>

<span data-ttu-id="87475-p102">L'organizzazione riceverà una notifica nel centro di messaggi Office 365 notifica che indica la data in cui verrà creato il criterio automatico nel tenant. Sono disponibili almeno un avviso di 30 giorni e che sia anche l'opzione per non ricevere messaggi. Uno scenario in cui si desidera potenzialmente esplicito è se si dispone di una soluzione di prevenzione della perdita di dati 3rd parti che già analizza per i tipi di riservati.</span><span class="sxs-lookup"><span data-stu-id="87475-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types.</span></span>

## <a name="new-policy-details"></a><span data-ttu-id="87475-109">Dettagli relativi al nuovo criterio</span><span class="sxs-lookup"><span data-stu-id="87475-109">New policy details</span></span>

<span data-ttu-id="87475-110">Verrà creata una nuova regola di flusso di posta elettronica di Exchange nell'organizzazione che verrà automaticamente crittografare i messaggi di posta elettronica di fuori dell'organizzazione con il *Solo crittografa* criteri che contengono i tipi di informazioni riservate seguenti:</span><span class="sxs-lookup"><span data-stu-id="87475-110">A new Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if they contain the following sensitive information types:</span></span>

- <span data-ttu-id="87475-111">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="87475-111">ABA routing number</span></span>
- <span data-ttu-id="87475-112">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="87475-112">Credit card Number</span></span>
- <span data-ttu-id="87475-113">Numero di Drug imposizione Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="87475-113">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="87475-p103">Usa / numero di passaporto Regno Unito</span><span class="sxs-lookup"><span data-stu-id="87475-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="87475-116">Numero di conto bancario negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="87475-116">U.S. bank account number</span></span>
- <span data-ttu-id="87475-117">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="87475-117">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="87475-118">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="87475-118">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="87475-119">I tipi di sensibili esatti possono variare dalle impostazioni locali dell'organizzazione e vengono comunicati nella notifica centro messaggi.</span><span class="sxs-lookup"><span data-stu-id="87475-119">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="87475-120">Che cosa è necessario eseguire per preparare la modifica</span><span class="sxs-lookup"><span data-stu-id="87475-120">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="87475-p104">Non è necessario aggiornare o modificare le impostazioni di configurazione di Office 365 esistente prima di questa modifica nuova. Tuttavia, si desidera aggiornare qualsiasi documentazione applicabile per l'utente finale e materiale di formazione per preparare gli utenti dell'organizzazione per la modifica.</span><span class="sxs-lookup"><span data-stu-id="87475-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span>

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="87475-123">Questa modifica rappresentare nel Registro di controllo?</span><span class="sxs-lookup"><span data-stu-id="87475-123">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="87475-p105">Questa attività è possibile controllare ed è disponibile per i clienti.  L'operazione è 'New-TransportRule' e un frammento di una voce di controllo di esempio di ricerca del Registro di controllo nel centro conformità e sicurezza è seguito:</span><span class="sxs-lookup"><span data-stu-id="87475-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="87475-126">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey specificato": "Microsoft operatore"," UserType": 3,"Version": 1,"carico di lavoro":"Di Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"UserId "," ":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX ( 15.20.1382.008)","Parameters": {"Nome":"Organizzazione","Il valore":" g 123456 221-12346"{"Nome":"ApplyRightsProtectionTemplate","Il valore":"Crittografa"}, {"Nome":"Name","Il valore":"Crittografare pubblicità riservati in uscita (da regola casella)"}, {"Nome":" MessageContainsDataClassifications"... e così via.*</span><span class="sxs-lookup"><span data-stu-id="87475-126">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="87475-127">Come escludere?</span><span class="sxs-lookup"><span data-stu-id="87475-127">How do I opt-out?</span></span>

<span data-ttu-id="87475-128">Se si desidera dissociare modifica, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="87475-128">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="87475-129">Connettersi a [Exchange Online PowerShell](https://aka.ms/exopowershell) come utente con ruolo amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="87475-129">Connect to [Exchange Online PowerShell](https://aka.ms/exopowershell) as a user with the global administrator role.</span></span>
2.  <span data-ttu-id="87475-130">Dopo l'autenticazione, eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="87475-130">Run the following code after authenticating:</span></span>

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a><span data-ttu-id="87475-131">Come è possibile disattivare il criterio automatico?</span><span class="sxs-lookup"><span data-stu-id="87475-131">How do I disable the automatic policy?</span></span>

<span data-ttu-id="87475-132">Se non escludere modifica e la regola di posta elettronica di Exchange sia stata già creata, è possibile [disabilitare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) passando a **flusso di posta** > **regole** in Exchange admin center (EAC) e disabilitare la regola "*Crittografa in uscita messaggi di posta elettronica riservati (fuori regola casella)*".</span><span class="sxs-lookup"><span data-stu-id="87475-132">If you didn’t opt-out of this change and the Exchange mail rule has already been created, you can [disable the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
