---
title: Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
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
ms.openlocfilehash: 892d04152d6029c48a52d37c6235d45a8ba67b81
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222815"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a>Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection

Se si è parte del team di sicurezza dell'organizzazione, è possibile integrare le funzionalità di Office 365 Advanced Threat Protection e Threat Intelligence con Windows Defender Advanced Threat Protection. In questo modo è possibile capire rapidamente se i computer degli utenti sono a rischio quando si esaminano le minacce in Office 365. Ad esempio, una volta abilitata l'integrazione, sarà possibile visualizzare un elenco di computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti che tali computer hanno in Windows Defender Advanced Threat Protection.
  
Nell'immagine seguente viene mostrata la scheda **dispositivi** che verrà visualizzata quando è abilitata l'integrazione di Windows Defender Advanced Threat Protection: 
  
![Quando Windows Defender ATP è abilitato, è possibile visualizzare un elenco di computer con avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica dispongono di quattro dispositivi e uno ha un avviso. Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel portale Windows Defender Advanced Threat Protection.
  
## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre di Office 365 Threat Intelligence e Windows Defender ATP.
    
- È necessario essere un amministratore globale di Office 365 o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato nel [centro conformità sicurezza &amp; ](https://protection.office.com). (Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- È necessario avere accesso sia a Office 365 Threat Intelligence sia al portale Windows Defender Advanced Threat Protection.
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a>Per integrare Office 365 Threat Intelligence con Windows Defender ATP

Integrazione di Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection è configurato utilizzando il centro conformità di Office 365 Security & e il portale Windows Defender Advanced Threat Protection.
  
1. In qualità di amministratore globale di Office 365 o amministratore della sicurezza, [https://protection.office.com](https://protection.office.com) accedere a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. 
    
2. Scegliere \> **Esplora** **gestione minacce** .<br>![Explorer nel menu Gestione minacce](media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.
    
4. Nella finestra di dialogo connessione ATP di Windows Defender, abilitare la connessione a Windows ATP.<br>![Connessione ATP Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Abilitare la connessione in Windows Defender Advanced Threat Protection. Per ulteriori informazioni, vedere [use the Windows Defender Advanced Threat Protection Portal](https://go.microsoft.com/fwlink/?linkid=859690).

  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

