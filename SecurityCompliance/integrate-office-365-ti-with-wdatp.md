---
title: Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection per visualizzare informazioni più dettagliate sulla gestione delle minacce.
ms.openlocfilehash: 640c073e9ef5b32ffaa8d38a426d86b60d80d2aa
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599052"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection

Se si è parte del team di sicurezza dell'organizzazione, è possibile integrare [Office 365 Advanced Threat Protection](office-365-atp.md) e le funzionalità di analisi e risposta correlate con [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). In questo modo è possibile capire rapidamente se i computer degli utenti sono a rischio quando si esaminano le minacce in Office 365. Ad esempio, una volta abilitata l'integrazione, sarà possibile visualizzare un elenco di computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti che tali computer hanno in Microsoft Defender Advanced Threat Protection.
  
Nell'immagine seguente viene mostrata la scheda **dispositivi** che verrà visualizzata quando è abilitata l'integrazione ATP di Microsoft Defender:
  
![Quando Microsoft Defender ATP è abilitato, è possibile visualizzare un elenco di computer con avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica dispongono di quattro dispositivi e uno ha un avviso. Se si fa clic sul collegamento di un dispositivo, la pagina verrà aperta nel centro protezione Microsoft Defender.
  
## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre di Office 365 ATP piano 2 (o Office 365 E5) e Microsoft Defender ATP.
    
- È necessario essere un amministratore globale di Office 365 o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato nel [centro conformità sicurezza &amp; ](https://protection.office.com). (Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- È necessario disporre dell'accesso sia all' [esploratore (o ai rilevamenti in tempo reale)](threat-explorer.md) nel centro sicurezza & compliance e al Centro protezione Microsoft Defender.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Per integrare Office 365 ATP con Microsoft Defender ATP

L'integrazione di Office 365 ATP con Microsoft Defender ATP è configurata utilizzando il Centro sicurezza & compliance e il Centro protezione Microsoft Defender.
  
1. In qualità di amministratore globale di Office 365 o amministratore della sicurezza, [https://protection.office.com](https://protection.office.com) accedere a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.
    
2. Scegliere \> **Esplora** **gestione minacce** .<br>![Explorer nel menu Gestione minacce](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.
    
4. Nella finestra di dialogo connessione ATP di Windows Defender, abilitare la connessione a Windows ATP.<br>![Connessione ATP Microsoft Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Abilitare la connessione nel centro protezione Microsoft Defender.

  
## <a name="related-topics"></a>Argomenti correlati

[Indagine e risposta alle minacce di Office 365](office-365-ti.md)
  
[Protezione avanzata dalle minacce di Office 365](office-365-atp.md)
  

