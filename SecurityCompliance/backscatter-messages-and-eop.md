---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. La DNSBL Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non si tratta di un elenco di spammer e non si tenta di rimuovere i server dal DNSBL di Backscatterer.
ms.openlocfilehash: 73f8631c50bcfb8a023b2b6007b7ccf48038e16e
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275296"
---
# <a name="backscatter-messages-and-eop"></a>Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP

I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. Poiché Exchange Online Protection (EOP) è un servizio di filtro della posta indesiderata, i messaggi di posta elettronica inviati a destinatari inesistenti e ad altre destinazioni sospette vengono rifiutati dal servizio. In questo caso, EOP genererà un messaggio di rapporto di mancato recapito (NDR) e lo riconsegnerà al "mittente". Poiché gli spammer utilizzano frequentemente un indirizzo contraffatto o non valido nei propri messaggi, l'indirizzo del mittente a cui viene inviato il rapporto di MANCAto reCAPITO può comportare un messaggio a dispersione. In questo caso, i server in uscita associati alla rete EOP possono essere elencati nell'elenco DNS bloccati di Backscatterer (DNSBL). La DNSBL Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non si tratta di un elenco di spammer e non si tenta di rimuovere i server dal DNSBL di Backscatterer. 
  
> [!TIP]
> In base alle istruzioni riportate sul sito Web Backscatterer, l'utilizzo della modalità di rifiuto per tutta la posta in arrivo non è una configurazione consigliata o un utilizzo appropriato del servizio. Deve essere utilizzato invece in modalità sicura. Per ulteriori informazioni sull'implementazione della corretta configurazione della posta indesiderata costituita da falsi rapporti di mancato recapito, visitare il [sito Web Backscatterer.org](http://www.backscatterer.org/?target=usage). 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Elenco IP Backscatterer.org](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
Vedere la voce "backscattering di rapporto di MANCAto reCAPITO" in [Advanced Spam Filtering Options](advanced-spam-filtering-asf-options.md)
  

