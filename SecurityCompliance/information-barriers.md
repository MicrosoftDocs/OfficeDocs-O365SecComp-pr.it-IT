---
title: Panoramica delle barriere informative
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare le barriere informative per garantire la conformità della comunicazione tramite Microsoft teams all'interno dell'organizzazione.
ms.openlocfilehash: a2c202d08f1de60f92f13b2ac4c2b9d3c7f900e8
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935938"
---
# <a name="information-barriers-preview"></a>Barriere informative (anteprima)

## <a name="overview"></a>Panoramica

I servizi cloud Microsoft includono potenti funzionalità di comunicazione e collaborazione. Tuttavia, si supponga di voler limitare le comunicazioni tra due gruppi per evitare che si verifichi un conflitto di interessi nell'organizzazione. In alternativa, è possibile limitare le comunicazioni tra alcune persone all'interno dell'organizzazione per salvaguardare le informazioni interne. Microsoft 365 consente la comunicazione e la collaborazione tra gruppi e organizzazioni, quindi è possibile limitare le comunicazioni tra i gruppi di utenti specifici, se necessario. Con barriere informative, è possibile! 

Le barriere informative sono ora in anteprima, a partire da Microsoft teams. Quando queste funzionalità sono disponibili per la propria organizzazione, un amministratore di conformità o di barriere informative può definire criteri che consentano o impediscano le comunicazioni tra i gruppi di utenti di Microsoft teams. I criteri di barriera delle informazioni possono essere utilizzati per situazioni come queste:

- Un trader diurno non può chiamare qualcuno del team di marketing
- Il personale finanziario che lavora su informazioni aziendali riservate non è in grado di ricevere chiamate da determinati gruppi all'interno dell'organizzazione
- Un team interno con materiale segreto commerciale non può chiamare o chattare online con persone di alcuni gruppi all'interno della propria organizzazione.
- Un team di ricerca può solo chiamare o chattare online con un team di sviluppo del prodotto

Per tutti questi scenari di esempio e altro ancora, è possibile definire i criteri di barriera delle informazioni per impedire o consentire le comunicazioni in Microsoft teams. Tali criteri possono impedire agli utenti di effettuare chiamate o chattare con coloro che non devono o consentire agli utenti di comunicare solo con gruppi specifici in Microsoft teams. Con i criteri di protezione delle informazioni in vigore, quando gli utenti interessati da tali criteri tentano di comunicare con altri membri di Microsoft teams, vengono eseguiti i controlli per impedire (o consentire) la comunicazione (come definito dai criteri di barriera delle informazioni). Per ulteriori informazioni sull'esperienza utente con barriere informative, vedere barriere informative [in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!NOTE]
> Gli ostacoli alle informazioni non si applicano alle comunicazioni di posta elettronica o alla condivisione di file tramite SharePoint Online o OneDrive.

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

**Attualmente, la caratteristica barriera informativa è in anteprima privata**. Quando queste funzionalità sono in genere disponibili, verranno incluse nelle sottoscrizioni, ad esempio:

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Microsoft 365 E5 Information Protection and Compliance

Per ulteriori informazioni, vedere [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

Per [definire o modificare criteri di barriera delle informazioni](information-barriers-policies.md), è necessario essere assegnati a uno dei ruoli seguenti:

- Microsoft 365 amministratore globale
- Amministratore globale di Office 365
- Amministratore di conformità
- Amministratore di barriere informative

È necessario avere familiarità con i cmdlet di PowerShell per definire, convalidare o modificare i criteri di barriera delle informazioni. Anche se vengono forniti diversi esempi di cmdlet di PowerShell nelle [informazioni su come](information-barriers-policies.md), è necessario conoscere ulteriori dettagli, ad esempio i parametri, per l'organizzazione.

## <a name="next-steps"></a>Passaggi successivi

- [Per ulteriori informazioni, vedere barriere informative in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [Visualizzare gli attributi che è possibile utilizzare per i criteri di barriera delle informazioni](information-barriers-attributes.md)
- [Definire i criteri per le barriere informative](information-barriers-policies.md) 

