---
title: Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: "Quando un mittente viene bloccato dal servizio a causa dell'invio di posta indesiderata in uscita, l'amministratore del dominio specificato quando si configura il criterio di posta indesiderata in uscita riceverà un messaggio di posta elettronica di notifica simile al seguente:"
ms.openlocfilehash: 94af965505f7541600a6cd7937ae881226a2ac79
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275476"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.

Quando un mittente viene bloccato dal servizio a causa dell'invio di posta indesiderata in uscita, l'amministratore del dominio specificato quando si [Configura il criterio di posta](configure-the-outbound-spam-policy.md) indesiderata in uscita riceverà un messaggio di posta elettronica di notifica simile al seguente: 
  
 **Indirizzo mittente:** spamalerts@microsoft.com 
  
 **Oggetto:** Notifica posta indesiderata in uscita - a \<  *account name*  \> è stato impedito di inviare posta indesiderata in uscita 
  
 **Corpo:** Si tratta di una risposta automatica del sistema di analisi di posta indesiderata di Exchange Online Protection. 
  
Sono stati rilevati volumi elevati di posta elettronica contrassegnata come posta indesiderata o altro comportamento sospetto da parte di questa organizzazione. Ai seguenti account di posta elettronica è stato impedito di inviare posta elettronica (continueranno a ricevere messaggi di posta elettronica):
  
\< *account name*  \> 
  
È probabile che questo account di posta elettronica sia stato compromesso. Attenersi alla seguente procedura:
  
1. Risolvere questo problema internamente effettuando le seguenti operazioni:
    
  - Modificare la password dell'account.
    
  - Determinare la modalità con cui l'account è stato compromesso.
    
  - Adottare precauzioni per garantire che tale vulnerabilità non venga sfruttata di nuovo.
    
  - Confermare che nella coda della posta in uscita siano stati cancellati tutti i messaggi incriminati.
    
2. Contattare il supporto tecnico Microsoft tramite il consueto canale di contatto.
    
3. Spiegare che a un utente è stato impedito di inviare posta elettronica e che il problema è stato gestito.
    
4. L'agente creerà un ticket di supporto con le informazioni fornite e riassegnerà la pratica per sbloccare il dominio o l'indirizzo di posta elettronica.
    
5. Dopo che l'indirizzo è stato sbloccato e non ci sono altri problemi in sospeso, si verrà informati e avvisati dello sblocco.
    
Grazie per l'aiuto offerto nel controllo della posta elettronica indesiderata.
  
Exchange Online Protection.
  
\*\*NOTA - Non rispondere a questo messaggio, in quanto è stato inviato da un indirizzo di posta elettronica che non viene controllato.\*\*
  
> [!TIP]
> È inoltre possibile contattare il supporto tramite le opzioni descritte in [Help and Support for EOP](eop/help-and-support-for-eop.md). 
  

