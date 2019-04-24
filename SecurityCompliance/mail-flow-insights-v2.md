---
title: Informazioni dettagliate sul flusso di posta nel Centro sicurezza e conformità
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Gli amministratori possono ottenere informazioni sul dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4af35fea640c1f4c43464d1adf2e4a9f3b4f780d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252110"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Informazioni dettagliate sul flusso di posta nel Centro sicurezza e conformità

> [!NOTE]
> Le funzionalità descritte in questo argomento non sono state distribuite in tutte le organizzazioni di Office 365 e sono soggette a modifiche.

Gli amministratori possono utilizzare il dashboard del flusso di posta elettronica nel centro sicurezza & Compliance per individuare le tendenze, le intuizioni e intraprendere azioni che consentono di risolvere i problemi relativi al flusso di posta nella propria organizzazione di Office 365.

Gli Insight, i report e i widget disponibili nel dashboard del flusso di posta sono i seguenti:

- [Rapporto Mappa del flusso di posta](mfi-mail-flow-map-report.md) (Questo rapporto è nuovo ed è attualmente in fase di distribuzione in Office 365).

- [Informazioni sullo stato del flusso di posta del dominio](mfi-domain-mail-flow-status-insight.md) (Questo Insight è nuovo ed è attualmente in fase di distribuzione in Office 365).

- [Report dei client auth SMTP](mfi-smtp-auth-clients-report.md) (Questo rapporto è nuovo ed è attualmente in fase di distribuzione in Office 365).

- [Insight sul dominio del mittente](mfi-sender-domain-insight.md) (Questo Insight è nuovo ed è attualmente in fase di distribuzione in Office 365).

- [Rapporto di mancato recapito](mfi-non-delivery-report.md) (Questo rapporto è nuovo ed è attualmente in fase di distribuzione in Office 365).

- [Rapporto di dominio non accettato](mfi-non-accepted-domain-report.md) (Questo rapporto è nuovo ed è attualmente in fase di distribuzione in Office 365).

- [Flusso di posta in ingresso e in uscita](mfi-outbound-and-inbound-mail-flow.md)

- [Avvisi di coda e code](mfi-queue-alerts-and-queues.md)

- [Report dei messaggi inoltrati automaticamente](mfi-auto-forwarded-messages-report.md)

- [Approfondimenti sul ciclo di posta](mfi-mail-loop-insight.md)

- [Approfondimenti sulle regole del flusso di posta lento](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Autorizzazioni necessarie per visualizzare il dashboard del flusso di posta

Il dashboard del flusso di posta è disponibile per:

- Membri del ruolo di **amministratore globale di Office 365** .

- Membri del ruolo di **amministratore di Exchange di Office 365** .

- Membri del **ruolo di amministratore del flusso di posta** nel centro sicurezza & Compliance. Se questo ruolo viene assegnato in modo esplicito a un utente che non è un membro dell'amministratore globale o dei ruoli di amministratore di Exchange:

  - L'utente deve accedere al centro sicurezza & Compliance direttamente su [https://protection.office.com](https://protection.office.com).

  - L'utente avrà solo l'autorizzazione di sola lettura per il dashboard del flusso di posta.

  - L'utente non potrà accedere al portale di amministrazione di Office 365.

Per ulteriori informazioni sul ruolo amministratore globale di Office 365, vedere [informazioni sui ruoli di amministratore di office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

Per informazioni sull'assegnazione di ruoli centro conformità di & per gli utenti, vedere [Give users access to the Security _AMP_ Compliance Center](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dove trovare il dashboard del flusso di posta

1. Accedere al centro sicurezza & Compliance all' [https://protection.office.com](https://protection.office.com)indirizzo.

2. Espande il **flusso di posta** e quindi seleziona **Dashboard**.

   ![Dashboard del flusso di posta nel centro conformità & sicurezza di Office 365](media/mail-flow-dashboard-v2.png)
