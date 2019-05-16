---
title: Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
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
description: Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection per visualizzare informazioni più dettagliate sulla gestione delle minacce.
ms.openlocfilehash: f6ea4309d3eb7a4ccd4987d221398d0f15994388
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077252"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a>Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection

Se si è parte del team di sicurezza dell'organizzazione, è possibile integrare Office 365 Advanced Threat Protection e le funzionalità di analisi e risposta correlate con Windows Defender Advanced Threat Protection. In questo modo è possibile capire rapidamente se i computer degli utenti sono a rischio quando si esaminano le minacce in Office 365. Ad esempio, una volta abilitata l'integrazione, sarà possibile visualizzare un elenco di computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti che tali computer hanno in Windows Defender Advanced Threat Protection.
  
Nell'immagine seguente viene mostrata la scheda **dispositivi** che verrà visualizzata quando è abilitata l'integrazione di Windows Defender Advanced Threat Protection: 
  
![Quando Windows Defender ATP è abilitato, è possibile visualizzare un elenco di computer con avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica dispongono di quattro dispositivi e uno ha un avviso. Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel portale Windows Defender Advanced Threat Protection.
  
## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre di Office 365 Advanced Threat Protection Plan 2 (o Office 365 E5) e Windows Defender ATP.
    
- È necessario essere un amministratore globale di Office 365 o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato nel [centro conformità sicurezza &amp; ](https://protection.office.com). (Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- È necessario avere accesso a Office 365 Threat Explorer nel centro sicurezza & compliance e nel portale Windows Defender Advanced Threat Protection.
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a>Per integrare Office 365 Advanced Threat Protection con Windows Defender ATP

Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection è configurato utilizzando il Centro sicurezza & compliance e il portale Windows Defender Advanced Threat Protection.
  
1. In qualità di amministratore globale di Office 365 o amministratore della sicurezza, [https://protection.office.com](https://protection.office.com) accedere a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. 
    
2. Scegliere \> **Esplora** **gestione minacce** .<br>![Explorer nel menu Gestione minacce](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.
    
4. Nella finestra di dialogo connessione ATP di Windows Defender, abilitare la connessione a Windows ATP.<br>![Connessione ATP Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Abilitare la connessione in Windows Defender Advanced Threat Protection. Per ulteriori informazioni, vedere [use the Windows Defender Advanced Threat Protection Portal](https://go.microsoft.com/fwlink/?linkid=859690).

  
## <a name="related-topics"></a>Argomenti correlati

[Indagine e risposta alle minacce di Office 365](office-365-ti.md)
  
[Protezione avanzata dalle minacce di Office 365](office-365-atp.md)
  

