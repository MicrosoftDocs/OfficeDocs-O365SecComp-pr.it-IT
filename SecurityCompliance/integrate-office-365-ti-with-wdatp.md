---
title: Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Integrare protezione rischio avanzate di Office 365 con Windows Defender avanzate rischio di protezione per visualizzare ulteriori informazioni sulla gestione di rischio.
ms.openlocfilehash: 48e879c1d41b5aa662f5128e234be91eb8225e7b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014768"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection

Se si fa parte del team di protezione dell'organizzazione, è possibile integrare Office 365 con Windows Defender avanzate Threat Protection (degli strumenti di analisi). Ciò consente di comprendere rapidamente se computer degli utenti sono a rischio durante l'analisi delle minacce in Office 365. Ad esempio, una volta integrazione è attivata, sarà in grado di visualizzare un elenco dei computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il modo in cui numero di avvisi recenti tali apparecchi sono in strumenti di analisi di Windows Defender.
  
Nell'immagine seguente è illustrata la scheda **dispositivi** che verrà visualizzato quando sono integrazione degli strumenti di analisi di Windows Defender abilitata: 
  
![Quando è abilitata degli strumenti di analisi di Windows Defender, è possibile visualizzare un elenco di computer con gli avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In questo esempio, è possibile visualizzare che i destinatari del messaggio di posta elettronica sono quattro macchine e uno con un avviso in strumenti di analisi di Windows Defender. Fare clic sul collegamento a un computer apre la pagina automatica in strumenti di analisi di Windows Defender in una nuova scheda.
  
## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre degli strumenti di analisi di Windows Defender e Business Intelligence di Office 365 rischio.
    
- È necessario essere un amministratore globale di Office 365 o disporre di un ruolo di amministratore di sicurezza assegnato nella versione di [protezione &amp; centro conformità](https://protection.office.com). (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md))
    
- È necessario avere accesso a Office 365 rischio Intelligence e portale degli strumenti di analisi di Windows Defender.
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Per l'integrazione di Business Intelligence di rischio di Office 365 con degli strumenti di analisi di Windows Defender

Integrazione di Business Intelligence di rischio di Office 365 con degli strumenti di analisi di Windows Defender è configurato in Office 365 e nel portale degli strumenti di analisi di Windows Defender.
  
1. Office 365 globale o un amministratore della sicurezza, passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola per Office 365. 
    
2. Scegliere **gestione rischio** \> **explorer rischio**.
    
3. **Ulteriori** dal menu, scegliere **Impostazioni WDATP**.
    
4. Selezionare **Connetti a Windows degli strumenti di analisi**.
    
Dopo avere modificato le impostazioni di Office 365, è necessario abilitare la connessione tra degli strumenti di analisi di Windows Defender. A tale scopo, vedere [utilizzo del portale di protezione di Windows Defender avanzate rischio](https://go.microsoft.com/fwlink/?linkid=859690).
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

