---
title: Creare criteri del tipo di informazioni sensibili per l'organizzazione con Office 365 Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Riepilogo: criteri di crittografia dei messaggi di Office 365 per i tipi di informazioni riservate.'
ms.openlocfilehash: 44966303ec7c58fdd82f733e1922073de848cf73
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834835"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a>Creare criteri del tipo di informazioni sensibili per l'organizzazione con Office 365 Message Encryption

È possibile utilizzare le regole del flusso di posta di Exchange o la prevenzione della perdita di dati (DLP) di Office 365 per creare un criterio tipo di informazioni riservate con la crittografia dei messaggi di Office 365. Per creare una regola del flusso di posta di Exchange, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Per creare il criterio mediante le regole del flusso di posta nell'interfaccia di amministrazione di Exchange

Accedere all'interfaccia di amministrazione di Exchange (EAC) e passare a **** > **regole**del flusso di posta. Nella pagina regole creare una regola che applica la crittografia dei messaggi di Office 365. È possibile creare una regola in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Per creare il criterio mediante le regole del flusso di posta in PowerShell

Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Utilizzare i cmdlet Set-IRMConfiguration e New-TransportRule per creare il criterio.

### <a name="example-mail-flow-rule-created-with-powershell"></a>Esempio di regola del flusso di posta creato con PowerShell

Eseguire i comandi seguenti in PowerShell per creare una regola del flusso di posta di Exchange che consente di crittografare automaticamente i messaggi inviati all'esterno dell'organizzazione con il criterio di *sola crittografia* se i messaggi di posta elettronica o i relativi allegati contengono le seguenti informazioni riservate tipi

- Numero di Routing ABA
- Numero di carta di credito
- Numero dell'agenzia di applicazione della droga (DEA)
- STATI UNITI/REGNO UNITO passport number
- Numero di conto corrente bancario degli Stati Uniti
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN)
- Stati Uniti - Numero di previdenza sociale (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a>Modalità di accesso degli allegati ai destinatari

Dopo che Office 365 ha crittografato un messaggio, i destinatari hanno accesso illimitato agli allegati quando accedono e aprono la posta elettronica crittografata.

## <a name="to-prepare-for-this-change"></a>Per preparare questa modifica

Potrebbe essere necessario aggiornare la documentazione per gli utenti finali applicabile e i materiali di formazione per preparare le persone all'interno dell'organizzazione per questa modifica. Condividere queste risorse di crittografia dei messaggi di Office 365 con gli utenti in base alle esigenze:

- [Inviare, visualizzare e rispondere a messaggi crittografati in Outlook per PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Video di Office 365 Essentials: crittografia dei messaggi di Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Visualizzare queste modifiche nel log di controllo

Office 365 verifica questa attività e la rende disponibile per gli amministratori di Office 365. L'operazione è' New-TransportRule ' e un frammento di una voce di controllo di esempio dalla ricerca del registro di controllo nel centro sicurezza & Compliance è riportato di seguito:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Per disabilitare o personalizzare i criteri dei tipi di informazioni riservate

Dopo aver creato la regola del flusso di posta di Exchange, è possibile [disabilitare o modificare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) accedendo alle**regole** del **flusso** > di posta nell'interfaccia di amministrazione di Exchange (EAC) e disabilitando la regola "crittografare i*messaggi di posta elettronica sensibili in uscita (regola fuori dalla casella)* ".
