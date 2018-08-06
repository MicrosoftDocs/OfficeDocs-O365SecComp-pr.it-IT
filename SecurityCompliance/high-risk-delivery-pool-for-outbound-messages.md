---
title: Pool di recapito ad alto rischio per i messaggi in uscita
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: Quando il sistema di posta elettronica del destinatario è stato danneggiato tramite un attacco dannoso posta indesiderata o malware e di invio di posta indesiderata in uscita tramite il servizio di filtraggio ospitato, con conseguenti gli indirizzi IP dei server di centro dati di Office 365 viene elencato nel blocco di terze parti elenchi.
ms.openlocfilehash: 856db53b105379ea3e606e39bf3c2612afa803c3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026623"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Pool di recapito ad alto rischio per i messaggi in uscita

Quando il sistema di posta elettronica del destinatario è stato danneggiato tramite un attacco dannoso posta indesiderata o malware e di invio di posta indesiderata in uscita tramite il servizio di filtraggio ospitato, con conseguenti gli indirizzi IP dei server di centro dati di Office 365 viene elencato nel blocco di terze parti elenchi. Server di destinazione è non utilizzare il servizio di filtraggio ospitato, ma utilizzare questi elenchi di blocco, rifiutare tutta la posta elettronica inviata da qualsiasi indirizzo IP filtraggio ospitato che è stati aggiunti a tali elenchi. Per evitare questo problema, tutti i messaggi in uscita che superano la soglia della posta indesiderata vengono inviati a un pool di recapito ad alto rischio. In questo pool secondario posta elettronica in uscita viene utilizzato solo per inviare i messaggi che possono essere di bassa qualità. Ciò consente di proteggere il resto della rete di inviare messaggi creati da più potrebbe provocare nell'indirizzo IP del mittente bloccato.
  
L'utilizzo di un pool di recapito ad alto rischio dedicati assicura che il pool in uscita normale solo invia messaggi conosciute di alta qualità. Utilizzo di questo pool IP secondario consente di ridurre la probabilità che il pool in uscita IP normale viene aggiunto a un elenco dei domini bloccati. La possibilità di essere messa in un elenco dei domini bloccati del pool di recapito ad alto rischio rimane un rischio. Questo è per impostazione predefinita.
  
I messaggi in cui il dominio di invio presenta alcun record indirizzo (record), che permette di utilizzare l'indirizzo IP del dominio, e nessun record MX, che consente ai server che devono ricevere posta elettronica per un dominio specifico nel sistema DNS posta diretta, vengono sempre indirizzati tramite il pool di recapito ad alto rischio indipendentemente dal fatto l'eliminazione della posta indesiderata.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>Informazioni sui messaggi di notifica stato recapito (DSN)

Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i messaggi (DSN) "animati" o "non riusciti".
  
Le cause possibili di un eccessivo numero di messaggi DSN sono:
  
- Una campagna di spoofing su uno dei clienti che utilizzano il servizio
    
- Un attacco directory harvest
    
- Un attacco di posta indesiderata
    
- Un server SMTP non autorizzato
    
Tutti questi problemi può comportare un aumento del numero di messaggi DSN elaborati dal servizio improvviso. In molti casi, questi messaggi DSN visualizzati come posta indesiderata per altri servizi e server di posta elettronica.
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Configurare i criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Domande frequenti sulla protezione anti-spam](anti-spam-protection-faq.md)
  

