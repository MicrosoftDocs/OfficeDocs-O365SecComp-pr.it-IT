---
title: Attivazione di Office 365 cloud app Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: Leggere questo articolo per informazioni su come abilitare Office 365 cloud app Security, alimentato da cloud app Security in Microsoft Azure.
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264128"
---
# <a name="turn-on-office-365-cloud-app-security"></a>Attivazione di Office 365 cloud app Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](activity-policies-and-alerts.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a>Attivazione di Office 365 cloud app Security

> [!IMPORTANT]
> Per eseguire l'attività seguente, è necessario essere un amministratore globale o un amministratore della sicurezza. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). Affinché Office 365 cloud app Security funzioni correttamente, **è necessario che la registrazione di controllo sia attivata** per l'ambiente Office 365. Per ulteriori informazioni, vedere [attivazione o disattivaZione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md). 
  
1. In qualità di amministratore globale o amministratore della sicurezza, [https://protection.office.com](https://security.microsoft.com) passare a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Passare a **avvisi** \> per la **gestione degli avvisi avanzati**.
    
3. Selezionare **attiva Office 365 cloud app Security**.
    
4. Scegliere **Vai a Office 365 cloud app Security**.<br/>![Nel centro sicurezza &amp; e conformità, scegliere Gestisci avvisi avanzati per accedere a Office 365 cloud app Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>In questo modo è possibile visualizzare i report e creare o modificare i criteri tramite il portale di sicurezza delle app cloud di Office 365.

Dopo aver attivato Office 365 cloud app Security, è possibile accedere al portale cloud app Security visitando [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) e accedendo.
    
> [!NOTE]
> Quando si attiva la sicurezza delle app cloud di Office 365, il controllo delle informazioni sugli account utente e sulle attività degli utenti di Office 365 viene trasferito a [Microsoft cloud app Security](https://aka.ms/whatiscas). In questo modo Office 365 fornisce avvisi avanzati, filtri e altre caratteristiche per ottenere informazioni e intraprendere azioni sulle attività sospette. 
  
## <a name="next-steps"></a>Passaggi successivi

- [Criteri attività](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento delle anomalie](anomaly-detection-policies-in-ocas.md)
    
- [Integrare il server SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Raggruppare gli indirizzi IP per semplificare la gestione](group-your-ip-addresses-in-ocas.md)
    

