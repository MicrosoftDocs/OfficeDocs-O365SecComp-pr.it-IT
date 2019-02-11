---
title: Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Integrare protezione rischio avanzate di Office 365 con Windows Defender avanzate rischio di protezione per visualizzare ulteriori informazioni sulla gestione di rischio.
ms.openlocfilehash: e5070e003972ae5308415dcdcca85b069d1163ac
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29382539"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection

Se si fa parte del team di protezione dell'organizzazione, è possibile integrare funzionalità di protezione di Office 365 avanzate rischio e Intelligence rischio con la protezione di Windows Defender avanzate rischio. Ciò consente di comprendere rapidamente se computer degli utenti sono a rischio durante l'analisi delle minacce in Office 365. Ad esempio, una volta integrazione è attivata, sarà in grado di visualizzare un elenco dei computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il modo in cui numero di avvisi recenti tali apparecchi dispongano di protezione di Windows Defender avanzate rischio.
  
Nell'immagine seguente è illustrata la scheda **dispositivi** che verrà visualizzato quando prevista l'integrazione con la protezione di Windows Defender avanzate rischio abilitato: 
  
![Quando è abilitata degli strumenti di analisi di Windows Defender, è possibile visualizzare un elenco di computer con gli avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In questo esempio, è possibile visualizzare che i destinatari del messaggio di posta elettronica dispongano di quattro dispositivi e uno con un avviso. Facendo clic sul collegamento di un dispositivo verrà visualizzata la relativa pagina del portale di protezione di Windows Defender avanzate rischio.
  
## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre degli strumenti di analisi di Windows Defender e Business Intelligence di Office 365 rischio.
    
- È necessario essere un amministratore globale di Office 365 o disporre di un ruolo di amministratore di sicurezza (ad esempio sicurezza amministratore) assegnato nella versione di [protezione &amp; centro conformità](https://protection.office.com). (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md))
    
- È necessario avere accesso a Business Intelligence di Office 365 rischio e il portale di protezione di Windows Defender avanzate rischio.
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Per l'integrazione di Business Intelligence di rischio di Office 365 con degli strumenti di analisi di Windows Defender

Integrazione di Business Intelligence di rischio di Office 365 con la protezione di Windows Defender avanzate rischio è configurato con entrambi i & di sicurezza di Office 365 centro conformità e il portale di protezione di Windows Defender avanzate rischio.
  
1. Un amministratore della sicurezza o un amministratore globale di Office 365, passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola per Office 365. 
    
2. Scegliere **gestione rischio** \> **Explorer**.<br>![Explorer menu Threat Management](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Nell'angolo superiore destro dello schermo, scegliere **Impostazioni WDATP**.
    
4. Nella casella degli strumenti di analisi di Windows Defender connessione della finestra attiva connessione a Windows degli strumenti di analisi.<br>![Connessione degli strumenti di analisi di Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Abilitare la connessione di protezione di Windows Defender avanzate rischio. Vedere [utilizzo del portale di protezione di Windows Defender avanzate rischio](https://go.microsoft.com/fwlink/?linkid=859690).

  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

