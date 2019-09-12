---
title: Esaminare e rispondere automaticamente alle minacce in Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Iniziare a utilizzare le funzionalità di risposta agli incidenti automatici in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: a7cec69fc7f739e065503121e456cc9bb3a34b31
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852758"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>Esaminare e rispondere automaticamente alle minacce in Office 365

## <a name="overview"></a>Panoramica

[Protezione avanzata dalle minacce di Office 365](office-365-atp.md) Nel piano 2 sono incluse le funzionalità di risposta agli incidenti automatici in grado di salvare il tempo e lo sforzo del team per le operazioni di sicurezza per gestire gli avvisi e le minacce. Leggere questo articolo per iniziare a usare AIR capabilities in Office 365. Per ulteriori informazioni sul funzionamento dell'aria, vedere [Automatic Incident Response (Air) in Office 365](automated-investigation-response-office.md).

Con l'aria, quando vengono attivati determinati avvisi, vengono avviati uno o più schemi di sicurezza e viene avviata un'indagine automatizzata. Durante e dopo un processo di analisi automatizzato, il team degli amministratori e delle operazioni di sicurezza può:

- [Visualizzare i dettagli di un'indagine](#view-details-of-an-investigation)

- [Esaminare e approvare le azioni in seguito a un'indagine](#review-and-approve-actions) 

- [Visualizzare i dettagli relativi a un avviso relativo a un'indagine](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale, un amministratore della sicurezza, un operatore di sicurezza o un lettore di sicurezza. Per ulteriori informazioni, vedere [Microsoft 365 Security Center: Roles and Permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).

## <a name="view-details-of-an-investigation"></a>Visualizzare i dettagli di un'indagine

1. In qualità di amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza [https://protection.office.com](https://protection.office.com) , accedere a e accedere. Questo porta al centro sicurezza & Compliance.

2. Eseguire una delle operazioni seguenti:

    - Andare al > **Dashboard**di **gestione delle minacce**. Questo porta al dashboard di [sicurezza](security-dashboard.md). I widget aria vengono visualizzati nella parte superiore del [dashboard di sicurezza](security-dashboard.md). Selezionare un widget, ad esempio **Riepilogo indagini**.

    - Andare a > **indagini**sulla **gestione delle minacce**. 

    Entrambi i metodi consentono di eseguire l'elenco delle indagini.

    ![Pagina di ricerca principale per AIR](media/air-maininvestigationpage.png) 

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** . Verrà aperta la pagina dei dettagli dell'analisi, a partire dal grafico di analisi.

    ![Pagina del grafico dell'indagine aerea](media/air-investigationgraphpage.png)

4. Utilizzare le varie schede per ulteriori informazioni sull'indagine.

## <a name="review-and-approve-actions"></a>Esaminare e approvare le azioni

In Office 365, le indagini automatizzate in genere determinano una o più azioni consigliate. Tuttavia, non vengono eseguite azioni finché non vengono approvate dal team di operazioni di sicurezza. Utilizzare la procedura seguente per esaminare e approvare le azioni.

1. In qualità di amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza [https://protection.office.com](https://protection.office.com) , accedere a e accedere. 

2. Andare a > **indagini**sulla **gestione delle minacce**.

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** . 

3. Nella visualizzazione dettagli analisi selezionare la scheda **azioni** . Tutte le azioni che sono in attesa di approvazione sono elencate qui.

4. Selezionare un elemento nell'elenco.

5. Selezionare **approva** per eseguire l'azione consigliata (o **rifiuta** per chiudere l'inchiesta senza intervenire).

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Visualizzare i dettagli relativi a un avviso relativo a un'indagine

Alcuni tipi di avvisi attivano l'analisi automatizzata in Office 365. Per ulteriori informazioni, vedere [Alerts](automated-investigation-response-office.md#alerts). Utilizzare la procedura seguente per visualizzare i dettagli relativi a un avviso associato a un'indagine automatizzata.

1. In qualità di amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza [https://protection.office.com](https://protection.office.com) , accedere a e accedere. Questo porta al centro sicurezza & Compliance.

2. Andare a > **indagini**sulla **gestione delle minacce**.

3. Nell'elenco delle indagini selezionare un elemento nella colonna **ID** . 

4. Per informazioni dettagliate sull'apertura di un'indagine, selezionare la scheda **avvisi** . Tutti gli avvisi che hanno attivato l'indagine sono elencati qui.

5. Selezionare un elemento nell'elenco. Verrà aperto un riquadro a comparsa con informazioni dettagliate sull'avviso e collegamenti a ulteriori operazioni.

6. Esaminare le informazioni nel riquadro a comparsa e, a seconda dell'avviso specifico, eseguire un'azione, ad esempio **risolvere**, **sopprimere**o **informare gli utenti**. 

    - La **risoluzione** equivale alla chiusura di un avviso
    
    - Non **consente a** un criterio di attivare avvisi per un determinato periodo di tempo
    
    - **Notify gli utenti** avviano un messaggio di posta elettronica con gli indirizzi di posta elettronica degli utenti già immessi e consentono al team di operazioni di sicurezza di digitare un testo per gli utenti. (Analogo all'invio di un messaggio ai destinatari tramite [Esplora minacce](threat-explorer.md)).  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Utilizzare l'API di attività di gestione di Office 365 per soluzioni di Reporting personalizzate o di terze parti

Se l'organizzazione utilizza una soluzione di report personalizzata o di terze parti, è possibile visualizzare le informazioni sulle indagini automatizzate in tale soluzione utilizzando l'API di attività di gestione di Office 365.

Per impostare questa impostazione, utilizzare le risorse seguenti:

|Risorsa  |Descrizione  |
|---------|---------|
|[Panoramica delle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory.         |
|[Iniziare a utilizzare le API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |L'API di gestione di Office 365 utilizza Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Office 365. Seguire la procedura descritta in questo articolo per configurare l'operazione.          |
|[Guida di riferimento all'API dell'attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare le informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Office 365 e Azure AD. Leggere questo articolo per ulteriori informazioni su come funziona.        |
|[Schema API di attività di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Ottenere una panoramica dello [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e dello [schema di analisi e risposta di Office 365 ATP and Threat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) per informazioni su tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.         |

## <a name="next-steps"></a>Passaggi successivi

[Ulteriori informazioni sugli avvisi](alert-policies.md)

[Trovare e studiare manualmente messaggi di posta elettronica dannosi che sono stati recapitati in Office 365](investigate-malicious-email-that-was-delivered.md)

[Informazioni su AIR in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[Visitare la Guida di orientamento di Microsoft 365 per vedere cosa succederà tra breve e in uscita](https://www.microsoft.com/microsoft-365/roadmap?filters=)