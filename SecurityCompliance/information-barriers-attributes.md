---
title: Attributi per i criteri di barriera delle informazioni
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare questo articolo come riferimento per i vari attributi che è possibile utilizzare nei criteri di barriera delle informazioni.
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668312"
---
# <a name="attributes-for-information-barrier-policies-preview"></a>Attributi per i criteri di barriera delle informazioni (anteprima)

Alcuni attributi in Azure Active Directory possono essere utilizzati per segmentare gli utenti. I segmenti vengono quindi utilizzati come filtri per i criteri di barriera delle informazioni. Ad esempio, è possibile utilizzare **Department** per definire segmenti di utenti per reparto all'interno dell'organizzazione (presupponendo che nessun singolo dipendente funzioni contemporaneamente per due reparti). 

In questo articolo viene fornito un elenco degli attributi che è possibile utilizzare. Per ulteriori informazioni sulle barriere informative, vedere le risorse seguenti:
- [Barriere informative (anteprima)](information-barriers.md)
- [Definire i criteri per le barriere informative in Microsoft Teams (anteprima)](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Come utilizzare gli attributi nei criteri di barriere informative

Gli attributi elencati in questo articolo possono essere utilizzati per definire (o modificare) segmenti di utenti. I segmenti vengono utilizzati come parametri (UserGroupFilter) nei criteri di barriera delle informazioni, come illustrato negli esempi seguenti:

|Esempio  |Cmdlet  |
|---------|---------|
|Definire un segmento denominato segment1 con l'attributo Department     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|Definire un segmento denominato Segmenta utilizzando l'attributo member (si supponga che questo attributo contenga nomi di gruppo, ad esempio "BlueGroup").     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|Definire un segmento denominato DayTraders tramite ExtensionAttribute1 (si supponga che questo attributo contenga titoli di lavoro, ad esempio "DayTrader").|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

Quando si definiscono i segmenti, utilizzare lo stesso attributo per tutti i segmenti. Ad esempio, se si definiscono alcuni segmenti utilizzando *Department*, definire tutti i segmenti che utilizzano *Department*. Non definire alcuni segmenti con *Department* e altri utenti che utilizzano *member*. Verificare che i segmenti non siano sovrapposti. ogni utente deve essere assegnato a un solo segmento. 

Per ulteriori informazioni, vedere [define Segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell).

## <a name="reference"></a>Riferimenti

Nella tabella seguente sono elencati gli attributi che è possibile utilizzare con le barriere informative.

|Nome della proprietà di Azure Active Directory (nome visualizzato LDAP)  |Nome della proprietà di Exchange  |
|---------|---------|
|Co       | Co        |
|Company     |Company         |
|Reparto     |Reparto         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |Alias |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|Posta   |WindowsEmailAddress    |
|Descrizione    |Descrizione    |
|MemberOf   |MemberOfGroup  |

## <a name="related-topics"></a>Argomenti correlati

[Definire i criteri per le barriere informative in Microsoft Teams (anteprima)](information-barriers-policies.md)

[Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)](information-barriers-troubleshooting.md)

[Barriere informative (anteprima)](information-barriers.md)



