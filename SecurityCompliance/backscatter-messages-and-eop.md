---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. Tale elenco contiene gli indirizzi IP che inviano messaggi di posta indesiderata costituita da falsi rapporti di mancato recapito. Non è un elenco di mittenti di posta indesiderata per cui i mittenti inclusi non vengono rimossi dai server.
ms.openlocfilehash: 7581255ce4e68f6eb661df280ecb0cb94b7515ef
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693365"
---
# <a name="backscatter-messages-and-eop"></a>Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP

I messaggi backscatter sono i messaggi di rimbalzo automatici inviati dai server di posta, in genere a causa della posta indesiderata in arrivo. Poiché EOP (Exchange Online Protection) è un servizio di filtro posta indesiderata, i messaggi di posta elettronica inviati a destinatari inesistenti a altri recapiti sospetti vengono rifiutati dal servizio. In questo caso EOP genera un messaggio di mancato recapito (NDR) e lo rispedisce al "mittente". Dal momento che i mittenti di posta indesiderata utilizzano spesso un indirizzo di invio contraffatto o non valido nei propri messaggi, l'indirizzo del mittente a cui viene inviata la notifica di mancato recapito potrebbe generare un messaggio contenente un falso rapporto di mancato recapito. Quando si verifica questa condizione, i server in uscita associati alla rete EOP possono essere elencati nell'elenco di indirizzi bloccati DNS della posta indesiderata costituita da falsi rapporti di mancato recapito (DNSBL). Tale elenco contiene gli indirizzi IP che inviano messaggi di posta indesiderata costituita da falsi rapporti di mancato recapito. Non è un elenco di mittenti di posta indesiderata per cui i mittenti inclusi non vengono rimossi dai server. 
  
> [!TIP]
> In base alle istruzioni riportate sul sito Web Backscatterer, l'utilizzo della modalità di rifiuto per tutta la posta in arrivo non è una configurazione consigliata o un utilizzo appropriato del servizio. Deve essere utilizzato invece in modalità sicura. Per ulteriori informazioni sull'implementazione della corretta configurazione della posta indesiderata costituita da falsi rapporti di mancato recapito, visitare il [sito Web Backscatterer.org](http://www.backscatterer.org/?target=usage). 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Elenco IP Backscatterer.org](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
Vedere la voce "backscattering di rapporto di MANCAto reCAPITO" in [Advanced Spam Filtering Options](advanced-spam-filtering-asf-options.md)
  

