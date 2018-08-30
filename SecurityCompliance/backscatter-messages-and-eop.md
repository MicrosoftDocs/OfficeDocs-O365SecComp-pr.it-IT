---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
ms.author: krowley
author: kccross
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
description: I messaggi backscatter sono i messaggi di rimbalzo automatizzato che vengono inviati dai server di posta elettronica, in genere a causa di posta indesiderata in ingresso. DNSBLHTTP:// Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non è un elenco di un mittente e non è tenta di rimuovere il server dalla DNSBLHTTP:// Backscatterer.
ms.openlocfilehash: 2ab5c6a3bec347446452acd3bdfd8c5d309994a9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002685"
---
# <a name="backscatter-messages-and-eop"></a>Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP

I messaggi backscatter sono i messaggi di rimbalzo automatizzato che vengono inviati dai server di posta elettronica, in genere a causa di posta indesiderata in ingresso. Perché Exchange Online Protection (EOP) è una servizio di filtraggio della posta indesiderata, messaggi di posta elettronica inviati a destinatari che non esistenti e ad altre destinazioni potenzialmente dannoso vengono respinto dal nostro servizio. In questo caso, EOP genererà un messaggio di rapporto di mancato recapito (NDR) e offre al "mittente". Poiché i mittenti di posta indesiderata utilizzano frequentemente un indirizzo contraffatto o non valido "In" nei loro messaggi, l'indirizzo del mittente in cui viene inviato il rapporto di mancato recapito può comportare un messaggio backscatter. In questo caso, server in uscita associati alla rete EOP possono essere elencati in Backscatterer DNS blocco elenco (DNSBLHTTP://). DNSBLHTTP:// Backscatterer è un elenco di indirizzi IP che inviano messaggi backscatter. Non è un elenco di un mittente e non è tenta di rimuovere il server dalla DNSBLHTTP:// Backscatterer. 
  
> [!TIP]
> In base alle istruzioni riportate sul sito Web Backscatterer, l'utilizzo della modalità di rifiuto per tutta la posta in arrivo non è una configurazione consigliata o un utilizzo appropriato del servizio. Deve essere utilizzato invece in modalità sicura. Per ulteriori informazioni sull'implementazione della corretta configurazione della posta indesiderata costituita da falsi rapporti di mancato recapito, visitare il [sito Web Backscatterer.org](http://www.backscatterer.org/?target=usage). 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Elenco IP Backscatterer.org](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
Vedere la voce "Backscatter rapporto di mancato recapito" in [Opzioni di filtro posta indesiderata](advanced-spam-filtering-asf-options.md)
  

