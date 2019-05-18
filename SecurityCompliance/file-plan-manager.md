---
title: Panoramica della gestione del piano file
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.
ms.openlocfilehash: 377589ab0a8fd2f4c5e73a21eac3988091fa3ed3
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152898"
---
# <a name="overview-of-file-plan-manager"></a>Panoramica della gestione del piano file

La gestione del piano file fornisce funzionalità avanzate per la gestione di criteri ed etichette di conservazione e consente di attraversare in modo integrato le attività con etichette ed etichetta-a-contenuto per l’intero ciclo di vita del contenuto, dalla creazione alla collaborazione, passando per la dichiarazione del record e la conservazione, all’eliminazione finale.

![Pagina del piano file](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a>Accesso alla gestione del piano file

I requisiti per accedere al piano file sono due:
- Un abbonamento a Office 365 Enterprise E5.
- L’utente dispone di uno dei ruoli seguenti nel Centro sicurezza e conformità:
    - Responsabile della conservazione
    - Responsabile della conservazione solo visualizzazione

## <a name="default-retention-labels-and-label-policy"></a>Etichette di conservazione e criteri di etichetta predefiniti

Se non sono presenti etichette conservazione nel Centro Sicurezza e Conformità, la prima volta in cui scegli **Piano file** nel riquadro di spostamento a sinistra, verrà creato un criterio di etichetta denominato **Criterio di pubblicazione di governance dei dati predefinito**. 

Questo criterio di etichetta contiene tre etichette di conservazione:

- **Procedura operativa**
- **Business general**
- **Accordo contrattuale**

Queste etichette di conservazione vengono configurate solo per conservare il contenuto, non per eliminare il contenuto. Questo criterio di etichetta verrà pubblicato per l'intera organizzazione e può essere disattivato o rimosso. 

È possibile stabilire chi ha aperto la gestione del piano file e avviato la first-run experience esaminando il log di controllo per le attività **Criteri di conservazione creati** e **Configurazione di conservazione creata per un criterio di conservazione**.

> [!NOTE]
> A causa di feedback di alcuni clienti, è stata rimossa la funzionalità che consente di creare le etichette di conservazione predefinite e i criteri di etichetta indicati in precedenza. Si vedranno solo questi criteri ed etichette se si utilizza la gestione piano file prima dell'11 aprile 2019.

## <a name="navigating-your-file-plan"></a>Esplorare il piano file

La gestione del piano file semplifica la visualizzazione unica delle impostazioni di tutti i criteri e le etichette di conservazione.

Si noti che le etichette di conservazione create all'esterno del piano file saranno disponibili nel piano file e viceversa.

Nella tabella **etichette piano file** sono disponibili le seguenti informazioni e funzionalità aggiuntive:

### <a name="label-settings-columns"></a>Colonne impostazioni etichetta

- **In base a** identifica il tipo di trigger che avvierà il periodo di conservazione. I valori validi sono:
    - Evento
    - Momento della creazione
    - Data ultima modifica
    - Data etichettatura
- **Record** indica se l'elemento diventa un record dichiarato dopo l'applicazione dell'etichetta. I valori validi sono:
    - No
    - Sì
    - Sì (normativo)
- **Conservazione** identifica il tipo di conservazione. I valori validi sono:
    - Conservare
    - Conservare ed eliminare
    - Eliminare
- **Disposizione** identifica cosa succederà al contenuto alla fine del periodo di conservazione. I valori validi sono:
    - null
    - Nessuna azione
    - Eliminazione automatica
    - Revisione obbligatoria (ovvero revisione della disposizione)

![Impostazioni delle etichette nel piano file](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a>Etichettare le colonne dei descrittori del piano file

È ora possibile includere altre informazioni nella configurazione delle etichette di conservazione. L’inserimento di descrittori del piano file nelle etichette migliora la gestibilità e l'organizzazione del piano file.

Per iniziare, la gestione del piano file fornisce alcuni valori predefiniti per: funzione/reparto, categoria, tipo di autorità e disposizione/citazione. È possibile aggiungere nuovi valori al descrittore del piano file quando si crea o si modifica un'etichetta di conservazione.

Ecco una visualizzazione del passaggio dei descrittori del piano file quando si crea o modifica un'etichetta di conservazione.

![Descrittori del piano file](media/file-plan-descriptors.png)

Ecco una visualizzazione delle colonne dei descrittori del piano file nella scheda etichette della gestione del piano file.

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a>Esportare le etichette dal piano file

Dalla gestione del piano file, è possibile esportare i dettagli di tutte le etichette di conservazione in un file CSV per agevolare le analisi di conformità periodiche con le parti interessate responsabili della governance dei dati all'interno dell'organizzazione.

Per esportare tutte le etichette di conservazione, passare a **gestione del piano file** \> **azioni del piano file** \> **esporta etichette**.

![Opzione per esportare il piano file](media/file-plan-export-labels-option.png)

Verrà aperto un file CSV che contiene tutte le etichette di conservazione esistenti.

![File CSV con tutte le etichette di conservazione](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a>Importare le etichette nel piano file

Dalla gestione del piano file, è possibile importare in blocco nuove etichette nonché modificare le etichette di conservazione esistenti.

Per importare nuove etichette di conservazione e aggiornare le etichette esistenti, passare a **gestione del piano file** \> **azioni del piano file** \> **importa etichette**.

![Opzione per importare il piano file](media/file-plan-import-labels-option.png)

![Opzione per scaricare un modello di piano file vuoto](media/file-plan-blank-template-option.png)

Scaricare un modello vuoto (o creare a partire da un'esportazione del piano file corrente).

![Modello di piano file vuoto aperto in Excel](media/file-plan-blank-template.png)

Compilare il modello (presto disponibili le informazioni di riferimento sui valori validi per le voci).

![Modello del piano file compilato con le informazioni](media/file-plan-filled-out-template.png)

Caricare il modello compilato e la gestione del piano file convaliderà le voci e visualizzerà le statistiche di importazione.

![Statistiche di importazione del piano file](media/file-plan-import-statistics.png)

Al termine dell'importazione, tornare alla gestione del piano file per assegnare nuove etichette ai criteri nuovi o esistenti.

![Opzione per pubblicare le etichette](media/file-plan-publish-labels-option.png)

