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
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>Criteri di crittografia dei messaggi di Office 365 per le informazioni riservate

In Office 365 tenant che verrà applicata la crittografia dei messaggi di Office 365 per tutti i messaggi di posta elettronica che contengono informazioni riservate e che vengono inviate all'esterno dell'organizzazione che verrà creata un nuovo criterio automatico. Questa nuova regola di flusso di posta elettronica di Exchange verrà creata automaticamente nel tenant Office 365 in modo che l'organizzazione verrà protetti per impostazione predefinita.

## <a name="when-to-expect-the-update-for-your-tenant"></a>Momento in cui si prevede che l'aggiornamento per il tenant

L'organizzazione riceverà una notifica nel centro di messaggi Office 365 notifica che indica la data in cui verrà creato il criterio automatico nel tenant. Sono disponibili almeno un avviso di 30 giorni e che sia anche l'opzione per non ricevere messaggi. Uno scenario in cui si desidera potenzialmente esplicito è se si dispone di una soluzione di prevenzione della perdita di dati 3rd parti che già analizza per i tipi di riservati. Ulteriori informazioni su come escludere sono disponibili più avanti in questo articolo.

## <a name="sensitive-information-type-policy-details"></a>Dettagli dei criteri tipo di informazioni riservate

Verrà creata una regola di flusso di posta di Exchange nell'organizzazione che verrà automaticamente crittografare i messaggi di posta elettronica di fuori dell'organizzazione con il *Solo crittografa* criteri che contengono i tipi di informazioni riservate seguenti:

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

Non è necessario aggiornare o modificare le impostazioni di configurazione di Office 365 esistente prima di questa modifica nuova. Tuttavia, si desidera aggiornare qualsiasi documentazione applicabile per l'utente finale e materiale di formazione per preparare gli utenti dell'organizzazione per la modifica. Condividere le risorse di Office 365 Message Encryption con gli utenti nel modo appropriato:

- [Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Office 365 Essentials Video: Crittografia dei messaggi Office](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>Questa modifica rappresentare nel Registro di controllo?

Questa attività è possibile controllare ed è disponibile per i clienti.  L'operazione è 'New-TransportRule' e un frammento di una voce di controllo di esempio di ricerca del Registro di controllo nel centro conformità e sicurezza è seguito:

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey specificato": "Microsoft operatore"," UserType": 3,"Version": 1,"carico di lavoro":"Di Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"UserId "," ":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX ( 15.20.1382.008)","Parameters": {"Nome":"Organizzazione","Il valore":" g 123456 221-12346"{"Nome":"ApplyRightsProtectionTemplate","Il valore":"Crittografa"}, {"Nome":"Name","Il valore":"Crittografare pubblicità riservati in uscita (da regola casella)"}, {"Nome":" MessageContainsDataClassifications"... e così via.*
 |

## <a name="how-do-i-opt-out"></a>Come escludere?

Se si desidera dissociare modifica, eseguire la procedura seguente:

1. Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).
2. Eseguire il cmdlet Set-IRMConfiguration come indicato di seguito:

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-the-automatic-policy"></a>Come è possibile disattivare il criterio automatico?

Se non escludere modifica e la regola di posta elettronica di Exchange sia stata già creata, è possibile [disabilitare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) passando a **flusso di posta** > **regole** in Exchange admin center (EAC) e disabilitare la regola "*Crittografa in uscita messaggi di posta elettronica riservati (fuori regola casella)*".
