---
title: Accesso con privilegi management in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni su con privilegi accedere management in Office 365
ms.openlocfilehash: 85141ae885132095692683b766d5550cc538e2e8
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29652261"
---
# <a name="privileged-access-management-in-office-365"></a>Accesso con privilegi management in Office 365

> [!IMPORTANT]
> In questo argomento vengono illustrate la distribuzione e configurazione indicazioni per la funzionalità attualmente disponibili solo in Office 365 E5 e avanzate SKU di conformità.

Accesso privilegiato management consente di controllare l'accesso granulare attività di amministrazione con privilegi in Office 365. È possibile proteggere dell'organizzazione da violazioni che possono utilizzare un account con privilegi di amministratore esistenti con la condizione accesso ai dati riservati o l'accesso alle impostazioni di configurazione critici. Dopo l'abilitazione della gestione dei privilegi di accesso, gli utenti dovranno richiedere l'accesso in tempo per eseguire attività con privilegi elevate e privilegiata attraverso un flusso di lavoro di approvazione altamente con ambito e specifici. In questo modo gli utenti appena sufficientemente accesso a eseguire attività in corso, senza mettere a rischio esposizione di dati riservati o le impostazioni di configurazione critico. Abilitazione della gestione dei privilegi di accesso in Office 365 all'organizzazione i mezzi operare con i privilegi zero la condizione e forniscono un livello di sistema di difesa contro le vulnerabilità derivanti a causa di questo tipo di accesso amministrativo la condizione.

Per una rapida panoramica delle integrata archivio protetto cliente e flusso di lavoro end-to-end con privilegi di accesso gestione, vedere l' [archivio protetto cliente e la gestione di privilegi di accesso in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Livelli di protezione

Accesso privilegiato gestione è complementare rispetto alle altre protezioni funzionalità dati e l'accesso all'interno dell'architettura di sicurezza di Office 365. Abilitazione della gestione dei privilegi di accesso come parte di un approccio integrato di sicurezza e protezione dell'organizzazione, un modello di sicurezza a più livelli è utilizzabile per ottimizzare la protezione delle informazioni riservate e le impostazioni di configurazione di Office 365. Come mostrato nella figura sotto abilitazione con privilegi consente di gestione di access si basa sulla protezione fornita con la crittografia nativa di Office 365 dati e il modello di sicurezza controllo di accesso basato sui ruoli di servizi di Office 365. Se utilizzata in combinazione con [la gestione delle identità con privilegi di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), questi due funzionalità fornire il controllo di accesso con l'accesso ad ambiti diversi nel tempo.

![Livelli di protezione di Office 365](media/pam-layered-protection.png)

Accesso privilegiato management in Office 365 possono essere definite e limitare l'ambito a livello di **attività** , mentre la gestione delle identità con privilegi di Azure Active Directory si applica protezione a livello di **ruolo** con la possibilità di eseguire più attività.  Azure Active Directory con privilegi Identity Management principalmente consente la gestione dei tipi di accesso per gruppi di ruoli e ruoli di Active Directory, durante l'accesso con privilegi management in Office 365 viene applicato solo a livello di attività.

- **Con privilegi di attivazione accedere management in Office 365 già utilizzando la gestione delle identità con privilegi di Azure Active Directory:** Aggiunta di gestione con privilegi di accesso in Office 365 offre un ulteriore livello dettagliato delle funzionalità di protezione e controllo di accesso ai dati di Office 365 con privilegi.

- **Abilitazione di Azure Active Directory privilegiato gestione delle identità durante l'utilizzo di già privilegiato gestione dell'accesso in Office 365:**  Aggiunta di gestione delle identità con privilegi di Azure Active Directory con privilegi gestione dell'accesso in Office 365 può estendere con privilegi di accesso ai dati all'esterno di Office 365 principalmente definita dal ruolo o l'identità dell'utente.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Flusso di architettura e il processo di gestione con privilegi di accesso

Ognuno dei flussi di processo seguenti strutturare l'architettura di accesso di privilegi e le relative modalità di interazione con il supporto di Office 365, il controllo di Office 365 e lo spazio di esecuzione di gestione di Exchange.

### <a name="step-1-configuring-a-privileged-access-policy"></a>Passaggio 1: Configurazione di un criterio di accesso con privilegi

Quando si configura un criterio di accesso con privilegi utilizzando l'interfaccia di amministrazione di Office 365 o Exchange Management PowerShell, creare e definire i criteri e la funzionalità di accesso privilegiato elabora gli attributi dei criteri nel supporto di Office 365 e i registri di impegno nella protezione di Office 365 e centro conformità. Il criterio sarà abilitata e pronto per la gestione delle richieste in arrivo per le approvazioni.

![Passaggio 1: creazione di criteri](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Passaggio 2: Richieste di accesso

Utilizzando l'interfaccia di amministrazione di Office 365 o Exchange Management PowerShell, gli utenti possono richiedere l'accesso alle attività con privilegi elevate o privilegiata. La funzionalità di accesso privilegiato invia la richiesta per il supporto di Office 365 per l'elaborazione in base ai criteri di accesso configurati principio dei privilegi e il sctivity dei record in Office 365 protezione e i registri centro conformità.

![Passaggio 2 - richieste di accesso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Passaggio 3: Approvazione accesso

Viene generata una richiesta di approvazione e il gruppo di approvazione riceve una notifica tramite posta elettronica di richiesta in sospeso. Se viene concessa l'approvazione, la richiesta di privilegi di accesso viene elaborata come un'approvazione e l'attività è pronto per essere completata. Se la richiesta viene negata, attività è bloccata e non consentire l'accesso viene concesso al reqeustor. Il richiedente riceverà una notifica dell'approvazione richieste o di tipo denial tramite messaggio di posta elettronica.

![Passaggio 3 - Access approval](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Passaggio 4: Elaborazione accesso

Per le richieste approvate, l'operazione viene elaborata per lo spazio di esecuzione di gestione di Exchange. L'approvazione viene confrontato con il criterio di accesso con privilegi ed elaborata da substrate Office 365. Tutte le attività per l'attività viene registrata nel Centro connessioni di Office 365 sicurezza e conformità.

![Passaggio 4 - elaborazione di Access](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>Quali SKU da utilizzare con privilegi di accesso in Office 365
Accesso privilegiato gestione è attualmente disponibile solo per i clienti con Office 365 E5 e avanzate SKU di conformità.

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>Quando sarà disponibile per Office 365 dei carichi di lavoro di là Exchange con privilegi di accesso?
Si intende offrire breve questa caratteristica in altri carichi di lavoro di Office 365. Quando si è pronti per condividere una sequenza temporale, verrà reso disponibile tramite [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>Le esigenze dell'organizzazione più di 30 accesso privilegiato criteri, viene aumentato questo limite?

Supponiamo incrementare il limite corrente 30 privilegiato criteri di accesso al più presto organizzazione Office 365.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>È necessario essere un amministratore globale per gestire l'accesso con privilegiato in Office 365?
No, è necessario che il ruolo di gestione dei ruoli di Exchange assegnato all'account che verranno gestiti con privilegi di accesso in Office 365. Il ruolo amministratore globale, tuttavia, questo ruolo sono incluse per impostazione predefinita e può essere utilizzato per gestire l'accesso con privilegiato se non si desidera configurare il ruolo di gestione dei ruoli come un'autorizzazione di account autonomo. Gli utenti che sono inclusi nel gruppo dei responsabili non necessario essere un amministratore globale o disporre del ruolo di gestione dei ruoli assegnato a verificare e approvare le richieste. 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>Quali sono le gestione accesso privilegiato in Office 365 correlati all'archivio protetto clienti?
[Archivio protetto cliente](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) consente a un livello di controllo di accesso per le organizzazioni per l'accesso ai dati dal provider di servizi, ad esempio Microsoft. Accesso privilegiato management in Office 365 consente il controllo di accesso granulare all'interno dell'organizzazione per tutte le attività di Office 365 con privilegi.
