---
title: Utilizzare le comunicazioni in Advanced eDiscovery (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 916691e1f2470ef9e9e54d9dfe06c5277a92ba53
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296089"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a>Utilizzare le comunicazioni in Advanced eDiscovery (Preview)

Advanced eDiscovery (Preview) consente ai servizi legali di semplificare i propri processi per il monitoraggio e la distribuzione delle notifiche di blocco legale. La funzionalità di comunicazione dei depositari consente ai servizi legali di gestire e automatizzare l'intero processo di conservazione legale: dalle notifiche, dai promemoria e dalle escalation, tutti in un'unica posizione.

## <a name="what-is-a-legal-hold-notification"></a>Che cos'è una notifica di conservazione legale?

Avviso di conservazione (noto anche come *blocco*per controversia legale) è una notifica inviata dal reparto legale di un'organizzazione ai dipendenti, al personale contingente o ad altri depositari di dati. Tali notifiche indicano ai depositari di conservare le informazioni archiviate elettronicamente (ESI), nonché i materiali che possono essere rilevanti per una questione legale attiva o imminente. I team legali devono sapere che ogni custode ha ricevuto, letto e compreso e ha accettato di conformarsi alle istruzioni fornite.

## <a name="the-legal-hold-notification-process"></a>Processo di notifica per il blocco legale

Un'organizzazione ha il dovere di conservare le informazioni rilevanti quando viene a conoscenza di una controversia legale imminente o di un'indagine di regolamentazione. Per soddisfare i requisiti di conservazione, l'organizzazione deve informare immediatamente i potenziali depositari del proprio dovere di preservare le informazioni rilevanti. 

Con Advanced eDiscovery (Preview), i team legali possono creare e personalizzare il flusso di lavoro di notifica per la conservazione legale. La funzionalità di comunicazione depositaria consente ai team legali di configurare le notifiche e i flussi di lavoro seguenti:

1. **Avviso di rilascio**: un avviso di conservazione legale viene emesso (o avviato) da una notifica del reparto legale ai depositari che potrebbero avere informazioni rilevanti sulla questione del caso. Questo avviso indica ai depositari di conservare tutte le informazioni che potrebbero essere necessarie per l'individuazione. 
   
2.  **Avviso**di riemissione: nel corso di un caso, è possibile che i depositari siano tenuti a conservare informazioni aggiuntive o meno rispetto a quelle precedentemente incaricate. Per questo scenario, è possibile aggiornare l'avviso di conservazione esistente e ripubblicarlo nei propri depositari.

3.  **Avviso di rilascio**: una volta risolto il problema e il custode non è più soggetto a un dazio di conservazione, il custode può essere rilasciato in modo che le informazioni non vengano più conservate se non necessario. Inoltre, il custode riceverà una notifica che non sono più in dovere di conservazione e con istruzioni su come riprendere la propria attività.

4. **Promemoria e**escalation: in alcuni casi, solo l'emissione di un avviso non è sufficiente per soddisfare i requisiti di individuazione legale. Con ogni notifica, i team legali possono programmare una serie di flussi di lavoro di promemoria e di escalation per il follow-up automatico con custodi insensibili.

    - **Promemoria**: dopo aver emesso o riemesso un avviso per la conservazione legale, un'organizzazione può impostare i promemoria per avvisare gli amministratori che non rispondono. 

    - **** Escalation: in alcuni casi, se un custode rimane inattivo anche dopo una serie di promemoria, il team legale può impostare un flusso di lavoro di escalation per notificare al custode e al suo responsabile.

## <a name="role-groups-and-permissions"></a>Gruppi di ruoli e autorizzazioni 

I team legali possono controllare e segmentare la propria attività di caso usando gruppi di ruoli e autorizzazioni di eDiscovery nel centro sicurezza & Compliance. 

Per creare e gestire notifiche di blocco legale, un utente deve far parte dei gruppi di ruoli seguenti:

- **eDiscovery Manager** : i membri di questo gruppo di ruoli possono creare e gestire i casi di eDiscovery. Sono in grado di aggiungere e rimuovere membri, inserire depositari e posizioni di contenuto in attesa, gestire le notifiche di archiviazione legale, creare e modificare le ricerche di contenuto associate a un caso, esportare i risultati di una ricerca di contenuto e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery (Preview). Sono presenti due gruppi secondari in questo gruppo di ruoli. La differenza tra questi sottogruppi è basata sull'ambito.

  - **eDiscovery Manager** -è in grado di visualizzare e gestire i casi di eDiscovery che creano o sono membri di. Se un altro Manager di eDiscovery crea un caso ma non aggiunge un secondo Manager di eDiscovery come membro del caso, il secondo responsabile di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina eDiscovery nel centro sicurezza & Compliance. i responsabili di eDiscovery possono inoltre accedere ai propri casi in Advanced eDiscovery (Preview) per eseguire attività di analisi.

  - **amministratore di eDiscovery** : consente di eseguire tutte le attività di gestione dei casi che un Manager di eDiscovery può eseguire. Inoltre, un amministratore di eDiscovery può:
    
    - Visualizzare tutti i casi elencati nella pagina eDiscovery.
    - Gestire qualsiasi caso nell'organizzazione dopo che si è aggiunto come membro del caso.
    - Accedere ai dati del caso in Advanced eDiscovery (Preview) per tutti i casi nell'organizzazione.

Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro conformità _AMP_ sicurezza di Office 365](../assign-ediscovery-permissions.md).