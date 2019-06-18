---
title: Archiviare i dati di terze parti in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Gli amministratori possono importare i dati di terze parti dalle piattaforme di social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti alle cassette postali nell'organizzazione di Office 365. In questo modo è possibile archiviare i dati da Facebook, Twitter e altre origini dati di terze parti in Office 365. È quindi possibile utilizzare e applicare le funzionalità di conformità di Office 365 (ad esempio, blocco legale, eDiscovery, archiviazione sul posto e criteri di conservazione) per i dati di terze parti.
ms.openlocfilehash: 796ad0314374dca60d1ff5f6b9317be491b757a1
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014605"
---
# <a name="archive-third-party-data-in-office-365"></a>Archiviare i dati di terze parti in Office 365

Office 365 consente agli amministratori di importare e archiviare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali dell'organizzazione di Office 365. Tra gli esempi di origini dati di terze parti che è possibile importare in Office 365 sono inclusi i servizi seguenti: 
  
- **Social** Networking: Facebook, LinkedIn, Twitter e Yammer 
    
- **Messaggistica istantanea** – Yahoo Messenger, GoogleTalk e Cisco Jabber 
    
- **Collaborazione documenti** – box e Dropbox 
    
- **Industrie verticali** – gestione delle relazioni con i clienti (come Salesforce Chatter) e servizi finanziari (come Bloomberg e Thomson Reuters) 
    
- **SMS/messaggi di testo** – BlackBerry 
    
Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio Blocco per controversia legale, eDiscovery, archiviazione sul posto, controllo, supervisione e criteri di conservazione di Office 365, a questi dati. Ad esempio, quando per una cassetta postale si attiva il blocco a causa di controversie legali, i dati di terze parti verranno mantenuti. È possibile eseguire la ricerca di dati di terze parti tramite gli strumenti di Microsoft eDiscovery. In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti esattamente come per i dati di Microsoft. In breve, l'archiviazione dei dati di terze parti in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

Esistono due modi per importare e archiviare i dati di terze parti in Office 365:

- **Utilizzare un connettore di dati di terze parti nel centro sicurezza & Compliance** – utilizzare un connettore di dati personalizzato disponibile nel centro sicurezza & conformità in Office 365. Dopo aver configurato e configurato il connettore, si connette all'origine dati di terze parti, converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale in Office 365. In questo momento, è possibile implementare i connettori per importare e archiviare i dati da pagine business di Facebook, account Twitter aziendale, Instant Bloomberg e LinkedIn. Per istruzioni dettagliate su come configurare un connettore, vedere:
   
   - **Facebook** : [utilizzare un connettore di esempio per archiviare i dati di facebook in Office 365](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter** : [utilizzare un connettore di esempio per archiviare i dati di twitter in Office 365](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn** – [configurare un connettore per archiviare i dati di linkedin in Office 365](archive-linkedin-data.md)

- **Collaborare con un partner Microsoft** : la propria organizzazione collabora con un partner Microsoft che fornirà un connettore personalizzato che verrà configurato per estrarre elementi dall'origine dati di terze parti (su base regolare) e quindi connettersi al cloud Microsoft da un API di terze parti e importare tali elementi in Office 365. Il connettore partner converte anche il contenuto di un elemento dall'origine dati di terze parti a un messaggio di posta elettronica e quindi le importa in una cassetta postale in Office 365. Per un elenco di partner che è possibile utilizzare e il processo dettagliato per questo metodo, vedere [collaborare con un partner per archiviare i dati di terze parti in Office 365](work-with-partner-to-archive-third-party-data.md).