---
title: Utilizzo delle comunicazioni di eDiscovery avanzate (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b27d6cca0382b18123cae4106f77ce0dcdf5e525
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607953"
---
# <a name="working-with-communications-in-advanced-ediscovery-preview"></a>Utilizzo delle comunicazioni di eDiscovery avanzate (Preview)

EDiscovery avanzate (Preview) consente al reparto legale di semplificare i processi intorno a gestione e la distribuzione delle notifiche di conservazione a fini giudiziari. La caratteristica di comunicazioni depositaria consente al reparto legale di gestire e automatizzare i processi di conservazione a fini giudiziari intera - da notifiche e promemoria escalation - tutti in un unico sito.

## <a name="what-is-a-legal-hold-notification"></a>Che cos'è una notifica di conservazione a fini giudiziari?

Un avviso di conservazione a fini giudiziari (noto anche come una *controversia attesa*) è una notifica inviata dall'ufficio legale dell'organizzazione per i dipendenti, personale temporaneo o depositari altri dati. Queste notifiche chiedere depositari per mantenere le informazioni archiviate in formato elettronico (ESI), nonché qualsiasi materiale che potrebbe essere rilevanti per un attivo o imminente del settore legale. I team legali importanti che ogni depositaria ha ricevuto, lettura, compresi e accettato di rispettare le istruzioni specificate.

## <a name="the-legal-hold-notification-process"></a>Processo di notifica di attesa legali

Un'organizzazione ha il compito di mantenere le informazioni rilevanti quando informato della presenza di un imminenti controversie o indagini normativi. Per rispettare i requisiti di archiviazione, l'organizzazione deve immediatamente informare depositari potenziali loro missione per mantenere le informazioni pertinenti. 

Con eDiscovery avanzate (anteprima), legale team possono creare e personalizzare il flusso di lavoro di notifica di conservazione a fini giudiziari. La caratteristica depositaria Communications consente ai team legali configurare le seguenti note e i flussi di lavoro:

1. **Avviso di rilascio**: un avviso di conservazione a fini giudiziari emissione (o avviato) da una notifica dall'ufficio legale di depositari che potrebbero avere informazioni relative ai caso materia. Questo avviso indica a tali depositari a mantengono le informazioni potrebbero essere necessari per l'individuazione. 
   
2.  **R-pubblicazione osservare**: durante un caso depositari potrebbero essere necessario conservare aggiuntive o meno informazioni di stati indicati in precedenza. Per questo scenario, è possibile aggiornare l'avviso di attesa esistente e nuova pubblicazione per la depositari.

3.  **Avviso di rilascio**: una volta scelta viene risolto e il depositaria non è più soggetta a un servizio di archiviazione, è possibile rilasciare il depositaria in modo che informazioni non è più viene mantenute se non necessarie. Inoltre, il depositaria riceverà una notifica che non sono più in servizio di archiviazione e le istruzioni in sospeso su come riprendere la propria attività.

4. **Le misure correttive e promemoria**: In alcuni casi, appena emissione di una notifica non è sufficiente per soddisfare esibizione legale. Con ogni notifica team legale consente di pianificare una serie di promemoria e riassegnazione flussi di lavoro automaticamente il completamento con depositari che non rispondono.

    - **Promemoria**: dopo un avviso di conservazione a fini giudiziari è stato emesso o nuovamente rilasciato a un insieme di depositari, un'organizzazione può impostare promemoria per notificare depositari che non rispondono. 

    - **Le misure correttive**: In alcuni casi, se un depositaria rimane che non rispondono anche dopo una serie di promemoria, il team legale possibile impostare un flusso di lavoro escalation per segnalare la depositaria e il suo manager.

## <a name="role-groups-and-permissions"></a>Le autorizzazioni e gruppi di ruoli 

Controllare e segmentare le attività caso utilizzando gruppi di ruoli correlati eDiscovery e le autorizzazioni in & la sicurezza centro conformità legale team. 

Per creare e gestire le notifiche di conservazione a fini giudiziari, un utente deve appartenere i gruppi di ruoli seguenti:

- **eDiscovery Manager** - membri di questo gruppo possono creare e gestire casi di eDiscovery. Può aggiungere e rimuovere membri, posizionare depositari e i percorsi di contenuti in attesa, gestire le notifiche di conservazione a fini giudiziari, creare e modificare ricerche del contenuto associato a un caso, esportare i risultati di una ricerca di contenuto e preparare i risultati della ricerca per l'analisi nella scheda Avanzate eDiscovery (Preview). Esistono due sottogruppi di questo gruppo di ruoli. La differenza tra questi sottogruppi si basa sull'ambito.

  - visualizzare e gestire casi di eDiscovery creano o membri di **eDiscovery Manager** . Se un altro eDiscovery Manager crea un caso ma non aggiungere un secondo eDiscovery Manager come membro di tale caso, il secondo eDiscovery Manager saranno in grado di visualizzare o aprire il caso nella pagina di eDiscovery in & la sicurezza centro conformità. eDiscovery Manager possono accedere anche i casi di eDiscovery avanzate (Preview) per eseguire attività di analisi.

  - **eDiscovery amministratore** - è possibile eseguire tutte le attività di gestione dei casi che può eseguire una ricerca eDiscovery Manager. Inoltre, un'amministratore di eDiscovery può:
    
    - Visualizzare tutti i casi elencati nella pagina eDiscovery.
    - Gestire tutti i casi nell'organizzazione dopo aggiungersi come membro del case.
    - Accedere ai dati casi di eDiscovery avanzate (Preview) per qualsiasi caso nell'organizzazione.

Per ulteriori informazioni, vedere [assegnare autorizzazioni di eDiscovery in & la protezione di Office 365 centro conformità](../assign-ediscovery-permissions.md).