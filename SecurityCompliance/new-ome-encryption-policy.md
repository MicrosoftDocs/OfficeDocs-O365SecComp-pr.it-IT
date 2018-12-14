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
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a>Nuovo criterio di crittografia dei messaggi di Office 365 per le informazioni riservate

In Office 365 tenant che verrà applicata la crittografia dei messaggi di Office 365 per tutti i messaggi di posta elettronica che contengono informazioni riservate e che vengono inviate all'esterno dell'organizzazione che verrà creata un nuovo criterio automatico. Questa nuova regola di flusso di posta elettronica di Exchange verrà creata automaticamente nel tenant Office 365 in modo che l'organizzazione verrà protetti per impostazione predefinita.

## <a name="how-will-this-work"></a>Come verrà questo tipo di lavoro?

L'organizzazione riceverà una notifica nel centro di messaggi Office 365 notifica che indica la data in cui verrà creato il criterio automatico nel tenant. Sono disponibili almeno un avviso di 30 giorni e che sia anche l'opzione per non ricevere messaggi. Uno scenario in cui si desidera potenzialmente esplicito è se si dispone di una soluzione di prevenzione della perdita di dati 3rd parti che già analizza per i tipi di riservati.

## <a name="new-policy-details"></a>Dettagli relativi al nuovo criterio

Verrà creata una nuova regola di flusso di posta elettronica di Exchange nell'organizzazione che verrà automaticamente crittografare i messaggi di posta elettronica di fuori dell'organizzazione con il *Solo crittografa* criteri che contengono i tipi di informazioni riservate seguenti:

- Numero di registrazione ABA
- Numero di carta di credito
- Numero di Drug imposizione Agency (DEA)
- Usa / numero di passaporto Regno Unito
- Numero di conto bancario negli Stati Uniti
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN)
- Stati Uniti - Numero di previdenza sociale (SSN)

> [!Note]
> I tipi di sensibili esatti possono variare dalle impostazioni locali dell'organizzazione e vengono comunicati nella notifica centro messaggi.

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Che cosa è necessario eseguire per preparare la modifica

Non è necessario aggiornare o modificare le impostazioni di configurazione di Office 365 esistente prima di questa modifica nuova. Tuttavia, si desidera aggiornare qualsiasi documentazione applicabile per l'utente finale e materiale di formazione per preparare gli utenti dell'organizzazione per la modifica.

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>Questa modifica rappresentare nel Registro di controllo?

Questa attività è possibile controllare ed è disponibile per i clienti.  L'operazione è 'New-TransportRule' e un frammento di una voce di controllo di esempio di ricerca del Registro di controllo nel centro conformità e sicurezza è seguito:

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey specificato": "Microsoft operatore"," UserType": 3,"Version": 1,"carico di lavoro":"Di Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"UserId "," ":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX ( 15.20.1382.008)","Parameters": {"Nome":"Organizzazione","Il valore":" g 123456 221-12346"{"Nome":"ApplyRightsProtectionTemplate","Il valore":"Crittografa"}, {"Nome":"Name","Il valore":"Crittografare pubblicità riservati in uscita (da regola casella)"}, {"Nome":" MessageContainsDataClassifications"... e così via.*
 |

## <a name="how-do-i-opt-out"></a>Come escludere?

Se si desidera dissociare modifica, eseguire la procedura seguente:

1. Connettersi a [Exchange Online PowerShell](https://aka.ms/exopowershell) come utente con ruolo amministratore globale.
2.  Dopo l'autenticazione, eseguire il codice seguente:

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a>Come è possibile disattivare il criterio automatico?

Se non escludere modifica e la regola di posta elettronica di Exchange sia stata già creata, è possibile [disabilitare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) passando a **flusso di posta** > **regole** in Exchange admin center (EAC) e disabilitare la regola "*Crittografa in uscita messaggi di posta elettronica riservati (fuori regola casella)*".
