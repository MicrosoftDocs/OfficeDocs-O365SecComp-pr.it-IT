---
title: Elenchi di mittenti attendibili e bloccati in Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione.
ms.openlocfilehash: fcb43f990750782788dc6f459dd5c7d296146a38
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028083"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Elenchi di mittenti attendibili e bloccati in Exchange Online

In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione. 
  
 *Vedere la versione aggiornata dei suggerimenti e delle procedure per la gestione di questi elenchi in qualità di amministratore in* [Impedire che i messaggi di posta elettronica legittimi vengano contrassegnati come posta indesiderata in Exchange Online Protection e Office 365](https://go.microsoft.com/fwlink/p/?LinkID=534224). 
  
Se non si è un amministratore e si desidera gestire la propria posta indesiderata in Outlook utilizzando un elenco di mittenti attendibili, vedere la procedura descritta nella panoramica di [Informazioni generali sul filtro per la posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=817222). 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Quali sono i limiti dei mittenti attendibili e bloccati in Exchange Online?

I limiti dei mittenti attendibili e bloccati in Exchange Online sono diversi da quelli di Active Directory e di Outlook. Tali limiti sono elencati di seguito:
  
- Limite dei mittenti attendibili: 1.024
    
- Limite dei mittenti bloccati: 500
    
Nota:
  
È possibile che si verifichi l'errore descritto in KB 2590466 ("Errore di convalida della posta indesiderata" in Outlook Web App per Exchange Server 2010). Per risolvere il problema, deselezionare la casella di controllo "Considera attendibili i messaggi di posta elettronica provenienti dai contatti personali". In alternativa, è possibile ridurre il numero di indirizzi di posta elettronica presenti nella cartella Contatti predefinita entro il limite massimo consentito di 1.024 in Exchange Online che è impostato per l'attributo "MaxSafeSenders". Per ulteriori informazioni sull'attributo e sul cmdlet Set-Mailbox, vedere l'argomento seguente:
  
[Set-Mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a>See also

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

