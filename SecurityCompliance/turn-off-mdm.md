---
title: Come disattivare la gestione dei dispositivi mobili in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: Eseguire la procedura seguente per arrestare criteri MDM impedita per i dispositivi mobili nella propria organizzazione Office 365.
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272221"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a>Come disattivare la gestione dei dispositivi mobili in Office 365

Per disattivare in modo efficace MDM per Office 365, rimuovere gruppi di utenti (definiti dai gruppi di sicurezza) dai criteri di gestione dei dispositivi o rimuovere i criteri di se stessi. 
  
- Rimuovere gruppi di utenti mediante la rimozione di gruppi di protezione utente dai criteri dispositivi che sono stati creati. 
    
- Rimozione di tutti i criteri per i dispositivi MDM disabilitare MDM per tutti gli utenti. 
    
Queste opzioni rimuoverà imposizione MDM per i dispositivi nell'organizzazione. Purtroppo è non è semplicemente "annullamento del provisioning" MDM per Office 365 dopo è stato configurato.
  
> [!IMPORTANT]
> Tenere presente l'impatto sulle dispositivi degli utenti quando si eliminano gruppi di protezione utente da criteri oppure rimuovere i criteri di se stessi. Ad esempio postaelettronica profili e messaggi di posta elettronica memorizzati nella cache può essere rimosso, in base al dispositivo. Vedere: [Qual è l'impatto dei criteri di protezione per diversi tipi di dispositivo?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a>Rimuovere i criteri dei dispositivi MDM gruppi di protezione utente

1. Accedere a **protezione &amp; centro conformità** \> **prevenzione della perdita di dati** \> **dei criteri di protezione di dispositivo**.
    
2. Selezionare un criterio dispositivi e fare clic su ![sull'icona Modifica](media/O365-MDM-CreatePolicy-EditIcon.gif) **modificare i criteri**.
    
3. In **distribuzione**, fare clic su **- rimuovere**.
    
    In **gruppi**, selezionare un gruppo di sicurezza.
    
4.  Fare clic su **Rimuovi**.
    
5. Fare clic su **Salva**.
    
## <a name="remove-mdm-device-policies"></a>Rimuovere i criteri dei dispositivi MDM

1. Accedere a **protezione &amp; centro conformità** \> **criteri di protezione** \> **criteri di protezione dispositivo**.
    
2. Selezionare un criterio del dispositivo e quindi fare clic su ![immagine del Cestino può icona. ](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Eliminare criteri**.
    
3. Nella finestra di dialogo **avviso** fare clic su **Sì**. 
    

