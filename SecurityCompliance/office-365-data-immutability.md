---
title: ImMutabilità dei dati di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Definisce e spiega l'immutabilità dei dati o i dati che devono essere individuabili e che non possono essere distrutti o modificati.
ms.openlocfilehash: b23a62dd95ec2ca554997fc667d89e6979e5b747
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262868"
---
# <a name="immutability-in-office-365"></a>Immutabilità in Office 365
Per alcune organizzazioni, la conformità alle normative, i requisiti di governance interna o il rischio di controversia legale richiedono la conservazione della posta elettronica e dei dati associati in un modulo individuabile. Tutti i dati del sistema devono essere individuabili e nessuno di essi può essere distrutto o alterato. Il termine standard del settore per questo è "immutabilità". 

I metodi tradizionali per ottenere l'immutabilità hanno in genere funzionato spostando i messaggi di posta elettronica in un percorso di archiviazione separato e di sola lettura. Sebbene tali sistemi servano allo scopo di preservare gli elementi delle cassette postali per l'individuazione, spesso influiscono sull'esperienza degli utenti in modo significativo rimuovendo gli elementi conservati dal flusso di lavoro giornaliero consueto. Per i professionisti IT, questo approccio all'immutabilità richiede la distribuzione e la manutenzione continua di un'infrastruttura di archiviazione e server separata. Lo stesso Discovery viene eseguito con gli strumenti esterni al sistema di posta elettronica, con i costi di distribuzione e manutenzione associati.

Tramite la configurazione delle caratteristiche dei criteri di conservazione e conservazione sul posto dell'archiviazione in Office 365 e in combinazione con i servizi nella famiglia di prodotti Office 365, ad esempio Exchange Online, SharePoint Online, OneDrive for business e Skype for business, l'archiviazione in Office 365 è in grado di conservare e mantenere numerose classi di dati in ingresso, interno e in uscita, tra cui:
- Comunicazioni di posta elettronica in ingresso e in uscita
- Libri e record contenuti in un modulo di posta elettronica o in documenti condivisi online
- Convocazioni di riunioni
- Fax
- Messaggi istantanei
- Documenti condivisi durante le riunioni online
- Voicemails

Inoltre, Microsoft ha sviluppato funzionalità per i componenti aggiuntivi per consentire l' [archiviazione di dati](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) da altre origini tramite l'integrazione con l'acquisizione di dati di terze parti e le soluzioni di gestione. Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365 ai dati, inclusi il blocco per controversia legale, la conservazione e il blocco sul posto, la ricerca di conformità, l'archiviazione sul posto, il controllo e i criteri di eDiscovery. Ad esempio, quando per una cassetta postale si attiva il blocco a causa di controversie legali, i dati di terze parti verranno mantenuti. È possibile cercare dati di terze parti mediante eDiscovery sul posto o Ricerca di conformità. In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti esattamente come per i dati di Microsoft. In breve, l'archiviazione dei dati di terze parti in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

L'archiviazione in Office 365 fornisce la regola 17a-4-conforme ai titoli e l'archiviazione di Exchange (SEC) e conserva i file permanenti di tutti i dati raccolti in un formato non riscrivibile e non cancellabile tramite criteri di conservazione sul posto e criteri di conservazione , incluso il blocco conservazione. In particolare:
- Tutti i record archiviati utilizzando i criteri di conservazione descritti in alto vengono conservati in un'area di archiviazione dedicata fuori dalla competenza dell'utente ordinario. Inoltre, solo gli utenti autorizzati possono accedere ai record e cercarli ma non modificarli o cancellarli.
- I metadati per ogni elemento includono un timestamp utilizzato per il calcolo della durata della conservazione. Gli indicatori di data e ora vengono applicati quando un nuovo elemento viene ricevuto o creato e non può essere modificato o rimosso successivamente dai metadati.
- L'archiviazione in Office 365 consente agli utenti di combinare diversi criteri di conservazione e di mantenere azioni per creare criteri di conservazione granulare per definire il tipo o la posizione degli elementi da immutabilmente preservati e la durata di tale conservazione.
- La funzionalità di blocco di conservazione consente agli utenti di scegliere se applicare un criterio restrittivo al criterio. Un criterio restrittivo impedisce a chiunque di avere la possibilità di rimuovere, disabilitare o apportare modifiche al criterio di conservazione. Questo significa che, una volta abilitato il blocco di conservazione, non può essere disabilitato e non esiste alcun meccanismo in base al quale i dati provenienti da depositari esistenti raccolti dai criteri di conservazione sul posto possono essere sovrascritti, modificati, cancellati o eliminati durante la periodo di conservazione. Inoltre, il periodo di attesa impostato dal blocco di conservazione non può essere ridotto o diminuito. Tuttavia, può essere allungato, nel caso di un requisito legale per continuare la conservazione dei dati archiviati, come indicato in alto. Il blocco conservazione garantisce che nessuno, neanche gli amministratori o gli utenti con un determinato accesso al controllo, possano modificare le impostazioni o sovrascrivere o cancellare i dati archiviati, portando l'archiviazione in Office 365 in linea con le indicazioni riportate nella versione 2003 di SEC. Regola 17a-4.

Per i clienti capire meglio come Office 365 può essere utilizzato per soddisfare gli obblighi normativi, in particolare per quanto riguarda i requisiti della regola 17a-4, è stato rilasciato un [white paper](https://go.microsoft.com/fwlink/?linkid=830440) che include l'archiviazione Exchange Online, SharePoint Online, OneDrive per le aziende e Skype for business. Il white paper fornisce inoltre un'analisi approfondita delle caratteristiche e delle funzionalità di archiviazione di Office 365 rispetto a ognuno dei requisiti previsti dalla regola 17a-4 di SEC e dimostra ai clienti regolamentati come l'archiviazione di Office 365 può consentire loro di soddisfare queste condizioni requisiti.