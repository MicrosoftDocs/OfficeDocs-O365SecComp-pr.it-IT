---
title: Immutabilità dati di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Definisce e viene illustrato l'immutabilità a dati o dati che devono essere individuabili e non può essere eliminato o modificato.
ms.openlocfilehash: 3a9e897734c1805e25a2e2dd5e0c5f8a3e3de3fd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531074"
---
# <a name="immutability-in-office-365"></a>Non modificabilità in Office 365
Per alcune organizzazioni, la conformità alle normative, i requisiti di governance interno o conservazione per controversia rischio richiedono la conservazione della posta elettronica e associare i dati di un modulo individuabile. Tutti i dati nel sistema devono risultare individuabili e non può essere eliminato o modificato. Il termine standard del settore per l'oggetto è "immutabilità." 

Metodi tradizionali di raggiungimento di immutabilità sono in genere ha avuto esito positivo per lo spostamento di messaggi di posta elettronica in un percorso di archiviazione separata di sola lettura. Mentre tali sistemi servono lo scopo di mantenimento degli elementi della cassetta postale per l'individuazione, spesso influiscono l'esperienza utente in modo significativo rimuovendo conservati gli elementi di flusso di lavoro giornaliero consuete. Per i professionisti IT, questa opzione per l'immutabilità richiede la distribuzione e la manutenzione di un'infrastruttura di server e archiviazione separata. Individuazione stesso viene eseguita con strumenti esterni per il sistema di posta elettronica, con distribuzione associato e i costi di manutenzione.

Configurazione delle caratteristiche dei criteri di conservazione dell'archiviazione in Office 365 e in combinazione con i servizi nel gruppo di Office 365, quali Exchange Online, SharePoint Online, di OneDrive for Business e Skype per le aziende e conservazione in locale archiviazione in Office 365 possono mantenere e mantenere molti tipi di dati in arrivo, interni e in uscita tra cui:
- Comunicazioni di posta elettronica in ingresso e in uscita
- Libri e i record contenuti nel modulo di posta elettronica o in documenti online condivisi
- Le convocazioni di riunione
- Fax
- Messaggi immediati
- Documenti condivisi durante le riunioni online
- Vocali non ascoltati diverso

Inoltre, Microsoft ha sviluppato funzionalità componente aggiuntivo per consentire [l'archiviazione dei dati](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) da altre origini grazie all'integrazione con soluzioni per la gestione e l'acquisizione dei dati di terze parti. Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365 per i dati, inclusi conservazione per controversia legale, In-Place eDiscovery e conservazione, ricerca di conformità, archiviazione sul posto, controllo e i criteri di conservazione. Ad esempio, quando una cassetta postale viene messo in attesa di conservazione per controversia, verranno mantenuti i dati di terze parti. È possibile cercare dati di terze parti tramite eDiscovery In locale o la ricerca di conformità. Oppure è possibile applicare l'archiviazione e i criteri di conservazione ai dati di terze parti nello stesso modo in cui è possibile utilizzare per i dati di Microsoft. In pratica, l'archiviazione dei dati di terze parti in Office 365 consentono alle organizzazioni garantire la conformità con criteri normativi e pubblico.

Archiviazione in Office 365 fornisce l'archiviazione 17 bis 4-compatibile con regola Securities and Exchange Commission (SEC) e consente di mantenere i file permanenti di tutti i dati raccolti in un formato non riscrivibile, cancellabili tramite criteri di conservazione e criteri di conservazione in locale , tra cui il blocco di conservazione. In modo specifico:
- Tutti i record archiviati utilizzando criteri di conservazione sopra riportati vengono mantenuti in un'area di archiviazione dedicate rientra dell'utente normale. Inoltre, solo gli utenti autorizzati accessibili e consente di cercare i record, ma non possono modificare oppure cancellarli.
- Metadati per ogni elemento contiene un timestamp utilizzata nel calcolo della durata di conservazione. Timestamp vengono applicate quando si riceve un nuovo elemento o creato e non possono essere successivamente modificate o rimosse dai metadati.
- L'archiviazione in Office 365 consente agli utenti di combinare i criteri di conservazione diversi e azioni per creare criteri di conservazione granulari per definire il tipo o il percorso degli elementi da conservare iimmutabile di archiviazione e la durata di tali conservazione.
- La funzionalità di archiviazione blocco consente agli utenti di scegliere se si desidera rendere il criterio di un criterio restrittivo. Un criterio restrittivo impedisce che la capacità di rimuovere, disabilitare o apportare modifiche al criterio di conservazione. Ciò significa che una volta blocco della conservazione è attivata, non può essere disattivata e non sarà presente alcun meccanismo in cui i dati da depositari esistente che sono stati raccolti per la conservazione implementate misure vengano sovrascritte, modificato, cancellare o eliminato durante la periodo di conservazione. Ulteriori informazioni, attesa blocco della conservazione per impostare periodi potrebbe non essere abbreviato o si diminuisce. Tuttavia, potrà essere allungati, nel caso di un requisito legale per continuare periodo di mantenimento dei dati archiviati, come indicato sopra. Blocco della conservazione assicura che nessuno, nemmeno administrators o con determinata controllare l'accesso, possono modificare le impostazioni o sovrascrivere o cancellare i dati che sono stati archiviati, portare l'archiviazione in Office 365 in linea con le indicazioni stabilite nella versione di secondo 2003 Regola 17 bis-4.

Per i clienti di comprendere meglio come è possibile utilizzare Office 365 per soddisfare le normative, in particolare in relazione ai requisiti di 17 bis 4 di regola, è stato reso disponibile un [white paper](https://go.microsoft.com/fwlink/?linkid=830440) che copra OneDrive archiviazione Exchange Online, SharePoint Online per le aziende e Skype per le aziende. Il white paper viene fornita un'analisi approfondita delle funzionalità di archiviazione di Office 365 e delle funzionalità su ciascuno dei requisiti in SEC regola 17 bis-4 anche e vengono illustrate ai clienti regolamentati come l'archiviazione di Office 365 possono consentire loro di soddisfare questi requisiti.