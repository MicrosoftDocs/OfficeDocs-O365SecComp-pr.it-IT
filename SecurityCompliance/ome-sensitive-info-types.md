---
title: Criteri di crittografia dei messaggi di Office 365 per informazioni riservate
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: i criteri di crittografia dei messaggi di Office 365 per i tipi di informazioni riservate sono ora disponibili.'
ms.openlocfilehash: 99cb7a9f94c9cf4036c11b74a5208ddf0e819ceb
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213980"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>Criteri di crittografia dei messaggi di Office 365 per informazioni riservate

Update (1/30/19): nell'ottobre 2018 abbiamo lavorato con un piccolo campione di clienti per capire se è possibile semplificare la protezione tramite la crittografia automatica dei messaggi di posta elettronica sensibili in base a determinati tipi di informazioni riservate. In base al feedback positivo di questo esempio, si è deciso di espandersi a un profilo più vario dei tenant nel dicembre 2018. Dopo aver comunicato il prossimo roll-out per selezionare i tenant, abbiamo ascoltato i commenti e abbiamo determinato che i clienti con ambienti più complessi volevano implementare le regole con maggiore cautela e quindi adeguare i piani.

Se l'organizzazione è stata selezionata per il roll-out a partire dal 15 gennaio 2019, non verrà eliminato il criterio automatico. Al contrario, vengono fornite istruzioni in questo articolo su come è possibile completare l'implementazione. Continuare a leggere per scoprire come.

||
|:-----|
|Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e professionisti IT. Se si cercano solo informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo che meglio si adatta alle proprie esigenze. |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a>Come creare il criterio tipo di informazioni riservate per il tenant

È possibile utilizzare le regole del flusso di posta di Exchange o la prevenzione della perdita di dati (DLP) di Office 365 per creare i criteri dei tipi di informazioni riservate. Per creare una regola del flusso di posta di Exchange, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Per creare il criterio mediante le regole del flusso di posta nell'interfaccia di amministrazione di Exchange

Accedere all'interfaccia di amministrazione di Exchange (EAC) e passare a**regole**del **flusso** > di posta. Creare una regola che applica la crittografia dei messaggi di Office 365 in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Per creare il criterio mediante le regole del flusso di posta in PowerShell

Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Utilizzare i cmdlet Set-IRMConfiguration e New-TransporRule per creare il criterio.

### <a name="example-mail-flow-rule-created-with-powershell"></a>Esempio di regola del flusso di posta creato con PowerShell

L'esecuzione dei comandi seguenti in PowerShell consente di creare una regola del flusso di posta di Exchange che consente di crittografare automaticamente i messaggi esterni all'organizzazione con il criterio di *sola crittografia* se i messaggi di posta elettronica o i relativi allegati contengono i seguenti elementi sensibili tipi di informazioni:

- Numero di Routing ABA
- Numero di carta di credito
- Numero dell'agenzia di applicazione della droga (DEA)
- Numero di passaporto Stati Uniti/Regno Unito
- Numero di conto corrente bancario degli Stati Uniti
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN)
- Stati Uniti - Numero di previdenza sociale (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a>Modalità di accesso degli allegati ai destinatari

Dopo che un messaggio è stato crittografato, i destinatari avranno accesso illimitato agli allegati una volta che accedono e aprono la posta elettronica crittografata.

## <a name="to-prepare-for-this-change"></a>Per preparare questa modifica

Potrebbe essere necessario aggiornare la documentazione per gli utenti finali applicabile e i materiali di formazione per preparare le persone all'interno dell'organizzazione per questa modifica. Condividere queste risorse di crittografia dei messaggi di Office 365 con gli utenti in base alle esigenze:

- [Inviare, visualizzare e rispondere a messaggi crittografati in Outlook per PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Video di Office 365 Essentials: crittografia dei messaggi di Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Visualizzare queste modifiche nel log di controllo

Questa attività è controllata ed è disponibile per gli amministratori di Office 365. L'operazione è' New-TransportRule ' e un frammento di una voce di controllo di esempio dalla ricerca del registro di controllo nel centro sicurezza & Compliance è riportato di seguito:

|     |
| --- |
| *{"CreationTime": "2018-11-28T23:35:01", "ID": "A1b2C3d4-DAA0-4c4f-A019-03a1234a1b0c", "Operation": "New-TransportRule", "IDOrganizzazione": "123456-221D-12345", "RecordType": 1, "ResultStatus": "true", "UserKey": "Microsoft operator", " UserType ": 3," Version ": 1," carico di lavoro ":" Exchange "," ClientIP ":" 123.456.147.68:17584 "," ObjectId ":" "," UserId ":" Microsoft operator","ExternalAccess":true,"OrganizationName":"contoso. onmicrosoft. com "," OriginatingServer ":" CY4PR13MBXXXX ( 15.20.1382.008) "," parametri ": {" nome ":" organizzazione "," valore ":" 123456-221D-12346 "{" Name ":" ApplyRightsProtectionTemplate consente "," value ":" Encrypt "}, {" Name ":" Name "," value ":" Encrypt Outbound emails sensitive (out of box Rule) "}, {" Name ":" MessageContainsDataClassifications "... ecc.* |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Per disabilitare o personalizzare i criteri dei tipi di informazioni riservate

Dopo aver creato la regola del flusso di posta di Exchange, è possibile [disabilitare o modificare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) accedendo alle**regole** del **flusso** > di posta nell'interfaccia di amministrazione di Exchange (EAC) e disabilitando la regola "crittografare i*messaggi di posta elettronica sensibili in uscita (regola fuori dalla casella)* ".
