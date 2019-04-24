---
title: Proteggere le app con Controllo app per l'accesso condizionale di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Interrompere le violazioni e le perdite in tempo reale con Office 365 cloud app Security Conditional Access App Control.
ms.openlocfilehash: d8370b1e02866db8f92ab7f6a46b06ddc3ed1055
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262988"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a>Proteggere le app con Controllo app per l'accesso condizionale di Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](ocas-deploy-conditional-access-app-control.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |

Nei luoghi di lavoro odierni, spesso non è sufficiente sapere cosa succede nell'ambiente cloud dopo il fatto. Si desidera arrestare le violazioni e le perdite in tempo reale, prima che i dipendenti imposti intenzionalmente o inavvertitamente i dati e l'organizzazione a rischio. È importante consentire agli utenti dell'organizzazione di sfruttare al meglio i servizi e gli strumenti disponibili nelle app cloud e far funzionare i propri dispositivi. Allo stesso tempo, è necessario disporre di strumenti che consentano di proteggere l'organizzazione dalle perdite di dati e dal furto dei dati in tempo reale. Insieme a Azure Active Directory, Office 365 cloud app Security offre queste funzionalità in un'esperienza olistica e integrata con il controllo delle app con accesso condizionale.

> [!IMPORTANT]
> per utilizzare il controllo delle app per l'accesso condizionale di cloud app security, è necessaria una  [licenza di Azure active Directory P1](https://azure.microsoft.com/pricing/details/active-directory/)e una sottoscrizione di sicurezza per l'app di [Office 365 cloud](office-365-cas-overview.md) attiva.

## <a name="how-it-works"></a>Funzionamento

Controllo delle app di accesso condizionale utilizza un'architettura proxy inverso ed è integrato in modo univoco con l'accesso condizionale di Azure AD. L'accesso condizionale di Azure AD consente di applicare i controlli di accesso alle app dell'organizzazione in base a determinate condizioni. Le condizioni definiscono *chi* (utente o gruppo di utenti) e *cosa* (quali app Cloud) e *dove* (quali posizioni e reti) viene applicato un criterio di accesso condizionale. Dopo aver determinato le condizioni, è possibile instradare gli utenti a Office 365 cloud app Security, in cui è possibile proteggere i dati con il controllo delle app con accesso condizionale applicando controlli di accesso e di sessione.

Il controllo delle app con accesso condizionale consente di monitorare e controllare le sessioni e l'accesso alle app degli utenti in tempo reale in base ai criteri di accesso e di sessione. I criteri di accesso e di sessione vengono utilizzati all'interno del portale cloud app Security per affinare ulteriormente i filtri e impostare azioni da intraprendere su un utente. Con i criteri di accesso e sessione, è possibile:

- **Blocca al download**: è possibile bloccare il download di documenti riservati. Ad esempio, nei dispositivi non gestiti.

- **Protect on download**: invece di bloccare il download di documenti sensibili, è possibile richiedere la protezione dei documenti tramite la crittografia al download. Questa crittografia garantisce che il documento sia protetto e che l'accesso utente sia autenticato se i dati vengono scaricati in un dispositivo non attendibile.

- **Monitorare le sessioni utente poco attendibili**: gli utenti rischiosi vengono monitorati quando eseguono l'accesso alle app e le loro azioni vengono registrate dall'interno della sessione. È possibile esaminare e analizzare il comportamento degli utenti per comprendere dove e in quali condizioni devono essere applicati i criteri di sessione in futuro.

- **Blocca accesso**: è possibile bloccare completamente l'accesso a specifiche app per gli utenti provenienti da dispositivi non gestiti o da reti non aziendali.

- **Creare la modalità**di sola lettura: monitorando e bloccando le attività personalizzate in-app, è possibile creare una modalità di sola lettura per applicazioni specifiche per utenti specifici.

- **Limitare le sessioni utente da reti non aziendali**: gli utenti che accedono a un'app protetta da una posizione che non fa parte della rete aziendale sono autorizzati ad accedere con restrizioni. Il download dei materiali sensibili è bloccato o protetto.

### <a name="how-session-control-works"></a>Funzionamento del controllo sessione

La creazione di un criterio di sessione con il controllo delle app di accesso condizionale consente di controllare le sessioni degli utenti reindirizzando l'utente tramite un proxy inverso anziché direttamente all'app. Da questo punto in poi, le richieste degli utenti e le risposte passano attraverso Office 365 cloud app Security invece che direttamente all'app.

Per mantenere l'utente all'interno della sessione, tutti gli URL rilevanti, gli script Java e i cookie all'interno della sessione dell'app vengono sostituiti con gli URL di sicurezza delle app cloud di Office 365. Ad esempio, se l'app restituisce una pagina con collegamenti i cui domini terminano con myapp.com, il collegamento viene sostituito con domini che terminano con qualcosa di simile a: myapp.com.us.cas.ms

Questo metodo non richiede l'installazione di alcuna operazione sul dispositivo. Questo metodo è ideale per il monitoraggio di sessioni provenienti da dispositivi non gestiti.

Dopo aver diretto una sessione tramite Office 365 cloud app Security, è possibile eseguire le operazioni seguenti:

1. Esaminare il traffico per le attività degli utenti

2. Visualizzare le attività identificate nel registro attività di protezione di Office 365 cloud app Security

3. Salvare i log del traffico e analizzarli

4. Consentire all'amministratore di esportare i log del traffico

5. Applicare i criteri nella sessione

## <a name="managed-device-identification"></a>Identificazione del dispositivo gestito

Il controllo delle app con accesso condizionale consente di creare criteri che considerano se un dispositivo viene gestito o meno. Per determinare se un dispositivo è gestito o meno, la caratteristica utilizza:

- Dispositivi conformi

- Dispositivi associati a un dominio

- Distribuzione dei certificati client

### <a name="compliant-and-domain-joined-devices"></a>Dispositivi conformi e appartenenti al dominio

L'accesso condizionale di Azure AD consente di passare direttamente alla sicurezza delle app cloud di Office 365. Da qui, è possibile sviluppare un criterio di accesso o un criterio di sessione che utilizza lo stato del dispositivo come filtro. Per ulteriori informazioni, vedere l' [Introduzione alla gestione dei dispositivi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).

### <a name="client-certificate-authenticated-devices"></a>Dispositivi autenticati del certificato client

Il meccanismo di identificazione del dispositivo può richiedere l'autenticazione dai dispositivi rilevanti utilizzando i certificati client. È possibile utilizzare i certificati client esistenti già distribuiti nell'organizzazione o distribuire nuovi certificati client ai dispositivi gestiti. È quindi possibile utilizzare la presenza di tali certificati per impostare i criteri di accesso e di sessione. Per informazioni su come distribuire i certificati client, vedere [deploy CONDIZIONAL Access App Control for Office 365 Apps](ocas-deploy-conditional-access-app-control.md).

## <a name="supported-apps-and-clients"></a>App e client supportati

Il controllo delle app di accesso condizionale per Office 365 supporta le seguenti app in primo piano:

- Exchange Online (anteprima)

- OneDrive for business (anteprima)

- Power BI (anteprima)

- SharePoint Online (anteprima)

- Microsoft Teams (anteprima)

- Yammer (anteprima)

Altre app vengono continuamente attivate per il controllo delle sessioni.

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire Controllo app per l'accesso condizionale per le app di Office 365](ocas-deploy-conditional-access-app-control.md)

- [Informazioni sui criteri di sessione in Office 365 cloud app Security](ocas-session-policies.md)

- [Informazioni sui criteri di accesso in Office 365 cloud app Security](ocas-access-policies.md) 