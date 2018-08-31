---
title: RGDP per condivisioni file locali
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: Informazioni su come gestire i requisiti GDPR nelle condivisioni file di Windows Server locale.
ms.openlocfilehash: 29f79f05f4b23656e3262b717e4fa24d80d9d470
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272451"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a>Condivide l'RGDP per le condivisioni file di Windows Server locale

L'approccio di base consigliato per le condivisioni file è il seguente:

-   Utilizzare Azure Information Protection per etichettare dati sensibili.

-   Utilizzare lo scanner di Azure Information Protection per individuare dati.

L'approccio consigliato per le condivisioni file include i seguenti passaggi:

1.  **Installare e configurare lo scanner di Azure Information Protection.**

    -   Scegliere i tipi di dati sensibili da usare.

    -   Specificare le cartelle locali e le condivisioni di rete da utilizzare.

2.  **Completare un ciclo di individuazione.**

    -   Eseguire lo scanner in modalità di individuazione e convalidare i risultati.

    -   Se necessario, ottimizzare le condizioni e i tipi di informazioni riservate.

    -   Valutare l'impatto previsto dell'applicazione automatica delle etichette.

3.  **Eseguire lo scanner di Azure Information Protection per applicare etichette a documenti idonei**.

4.  **Per la protezione:**

    -   Configurare le regole di prevenzione della perdita dei dati di Exchange per proteggere i documenti con l'etichetta desiderata.

    -   Assicurarsi di utilizzare le autorizzazioni per definire chi può accedere ai file.

5.  **Per il monitoraggio, integrare i log di Windows Server con uno strumento informazioni di sicurezza e gestione degli eventi.**

    -   Per trovare i dati personali per le richieste dell'interessato, usare uno scanner di Azure Information Protection. È anche possibile configurare una ricerca per indicizzazione nelle condivisioni file di SharePoint Server.

Per ulteriori informazioni sull'uso dello scanner di Azure Information Protection per individuare ed etichettare dati personali, vedere Microsoft GDPR Data Discovery Toolkit in [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>).

Per informazioni sulla configurazione dello scanner per le condizioni e l'utilizzo con tipi di informazioni riservate di prevenzione della perdita dei dati di Office 365, vedere [Come configurare le condizioni per la classificazione automatica e consigliata per Azure Information Protection](https://docs.microsoft.com/it-IT/information-protection/deploy-use/configure-policy-classification). Si noti che i nuovi tipi di informazioni riservate di Office 365 non saranno immediatamente disponibili per l'uso con lo scanner e che i tipi di informazioni riservate personalizzate non possono essere usati con lo scanner.
