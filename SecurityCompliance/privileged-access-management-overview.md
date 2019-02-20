---
title: Gestione degli accessi con privilegi in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni sulla gestione degli accessi con privilegi in Office 365
ms.openlocfilehash: 78107ceb497a546ef4d19ba33b8b72ec1406de1b
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090798"
---
# <a name="privileged-access-management-in-office-365"></a>Gestione degli accessi con privilegi in Office 365

> [!IMPORTANT]
> In questo argomento vengono illustrate le linee guida per la distribuzione e la configurazione per le funzionalità disponibili solo in Office 365 E5 e SKU di conformità avanzate.

La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365. Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account di amministrazione privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche. Dopo aver abilitato la gestione degli accessi con privilegi, gli utenti dovranno richiedere l'accesso just-in-time per completare le attività elevate e privilegiate tramite un flusso di lavoro di approvazione estremamente ambito e con un limite di tempo. Questo consente agli utenti di accedere in modo sufficiente per eseguire l'attività a portata di mano, senza rischiare l'esposizione di dati sensibili o di impostazioni di configurazione critiche. L'abilitazione della gestione degli accessi con privilegi in Office 365 consentirà all'organizzazione di operare con privilegi zero in piedi e di fornire un livello di difesa contro le vulnerabilità derivanti dall'accesso amministrativo permanente.

Per una breve panoramica dell'archivio protetto dei clienti integrato e del flusso di lavoro end-to-end per la gestione degli accessi con privilegi, vedere questo [Archivio per i clienti e la gestione degli accessi con privilegi in Office 365](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Livelli di protezione

La gestione degli accessi con privilegi integra altre protezioni di funzionalità di accesso e di dati all'interno dell'architettura di sicurezza di Office 365. Abilitando la gestione degli accessi con privilegi come parte di un approccio integrato alla sicurezza e alla protezione dell'organizzazione, è possibile utilizzare un modello di sicurezza sovrapposto per massimizzare la protezione delle informazioni riservate e delle impostazioni di configurazione di Office 365. Come illustrato nel diagramma seguente, l'abilitazione della gestione degli accessi con privilegi consente la creazione di una protezione fornita con la crittografia nativa dei dati di Office 365 e il modello di sicurezza dei servizi di Office 365 basato sui ruoli. Quando viene utilizzato in combinazione con [Azure ad privilegEd Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), queste due funzionalità forniscono il controllo di accesso con accesso just-in-time a diversi ambiti.

![Protezione a più livelli in Office 365](media/pam-layered-protection.png)

La gestione degli accessi con privilegi in Office 365 può essere definita e portata a livello di **attività** , mentre Azure ad Privileged Identity Management applica la protezione a livello di **ruolo** con la possibilità di eseguire più attività.  Azure AD Privileged Identity Management consente principalmente la gestione degli accessi per i ruoli di Active Directory e i gruppi di ruoli, mentre la gestione degli accessi con privilegi in Office 365 viene applicata solo a livello di attività.

- **Abilitazione della gestione degli accessi con privilegi in Office 365 mentre è già in uso Azure ad privilegEd Identity Management:** L'aggiunta di gestione degli accessi con privilegi in Office 365 fornisce un altro livello granulare di funzionalità di protezione e controllo per l'accesso privilegiato ai dati di Office 365.

- **Abilitazione di Azure ad privilegEd Identity Management già utilizzando la gestione degli accessi con privilegi in Office 365:**  L'aggiunta di Azure AD Privileged Identity Management alla gestione degli accessi con privilegi in Office 365 può estendere l'accesso privilegiato ai dati esterni a Office 365 che sono principalmente definiti dal ruolo o dall'identità di un utente.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architettura e flusso di processo di gestione degli accessi con privilegi

Ognuno dei seguenti flussi di processo descrive l'architettura dell'accesso di priveleged e il modo in cui interagisce con il substrato di Office 365, il controllo di Office 365 e l'Exchange Management Runspace.

### <a name="step-1-configuring-a-privileged-access-policy"></a>Passaggio 1: configurazione di un criterio di accesso privilegiato

Quando si configura un criterio di accesso privilegiato utilizzando l'interfaccia di amministrazione di Office 365 o Exchange Management PowerShell, si crea e si definisce il criterio e la funzionalità di accesso privilegiato elabora gli attributi dei criteri nel supporto di Office 365 e registra il attività nel centro sicurezza e conformità di Office 365. Il criterio è ora abilitato e pronto per gestire le richieste in arrivo per le approvazioni.

![Passaggio 1: creazione di criteri](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Passaggio 2: richiesta di accesso

Utilizzando l'interfaccia di amministrazione di Office 365 o Exchange Management PowerShell, gli utenti possono richiedere l'accesso a attività elevate o privilegiate. La funzionalità accesso privilegiato Invia la richiesta al substrato Office 365 per l'elaborazione in base ai criteri di accesso ai privilegi configurati e registra Sctivity nei registri del Centro sicurezza e conformità di Office 365.

![Passaggio 2-richiesta di accesso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Passaggio 3: accesso all'approvazione

Viene generata una richiesta di approvazione e il gruppo di approvazione riceve una notifica tramite posta elettronica della richiesta in sospeso. Se viene concessa l'approvazione, la richiesta di accesso privilegiato viene elaborata come approvazione e l'attività è pronta per essere completata. Se la richiesta viene negata, l'attività viene bloccata e non viene concesso alcun accesso all'reqeustor. Il richiedente riceverà una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.

![Passaggio 3-approvazione dell'accesso](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Passaggio 4: accedere all'elaborazione

Per le richieste approvate, l'attività viene elaborata da Exchange Management Runspace. L'approvazione viene controllata rispetto al criterio di accesso privilegiato ed elaborata dal supporto di stampa di Office 365. Tutte le attività per l'attività vengono registrate nel centro sicurezza e conformità di Office 365.

![Passaggio 4-elaborazione dell'accesso](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>Quali SKU è necessario utilizzare per l'accesso con privilegi in Office 365?
La gestione degli accessi con privilegi è attualmente disponibile solo per i clienti con Office 365 E5 e SKU di conformità avanzate.

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>Quando sarà disponibile l'accesso con privilegi per i carichi di lavoro di Office 365 al di fuori di Exchange?
Si prevede di offrire questa funzionalità in altri carichi di lavoro di Office 365 al più presto. Quando si è pronti a condividere una sequenza temporale, sarà disponibile tramite la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>La mia organizzazione ha bisogno di più di 30 poliziotti con accesso privilegiato, questo limite verrà aumentato?

Si prevede di aumentare al più presto il limite corrente di 30 criteri di accesso privilegiato per l'organizzazione di Office 365.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>È necessario essere un amministratore globale per gestire l'accesso con privilegi in Office 365?
No, è necessario che il ruolo di gestione dei ruoli di Exchange sia assegnato agli account che gestiscono l'accesso con privilegi in Office 365. Tuttavia, il ruolo di amministratore globale include questo ruolo per impostazione predefinita e può essere utilizzato per gestire l'accesso con privilegi se non si desidera configurare il ruolo di gestione dei ruoli come autorizzazione Account autonomo. Gli utenti inclusi in un gruppo dei responsabili approvazione non devono essere un amministratore globale o avere il ruolo di gestione dei ruoli assegnato per esaminare e approvare le richieste. 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>In che modo la gestione degli accessi con privilegi in Office 365 è relativa all'archivio protetto dei clienti?
L' [archivio protetto dei clienti](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) consente a un livello di controllo di accesso per le organizzazioni di accedere ai dati dal proprio provider di servizi, ad esempio Microsoft. La gestione degli accessi con privilegi in Office 365 consente il controllo di accesso granulare all'interno di un'organizzazione per tutte le attività di Office 365.
