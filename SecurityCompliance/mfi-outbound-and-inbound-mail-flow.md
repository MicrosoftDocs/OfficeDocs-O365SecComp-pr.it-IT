---
title: Flusso di posta in ingresso e in uscita
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Gli amministratori possono ottenere informazioni sul widget del flusso di posta in uscita e in ingresso nel dashboard del flusso di posta in Office 365 Security & Compliance Center.
ms.openlocfilehash: 98806a699909056b4295911a031bb7b14233ede5
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454888"
---
# <a name="outbound-and-inbound-mail-flow"></a>Flusso di posta in ingresso e in uscita

Il widget **flusso di posta in uscita e in ingresso** combina le informazioni del **rapporto del connettore** e del precedente rapporto di **Panoramica TLS** in un'unica posizione.

![Il rapporto flusso di posta in uscita e in ingresso nel dashboard del flusso di posta in Office 365 Security & Compliance Center](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

Le informazioni contenute nel widget sono correlate ai connettori e alla protezione dei messaggi TLS in Office 365. Per ulteriori informazioni, vedere gli argomenti riportati di seguito:

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Come viene utilizzato TLS per proteggere il traffico della posta elettronica in Office 365](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>Protezione dei messaggi in transito (tramite TLS)

Il widget **flusso di posta in uscita e in ingresso** Visualizza la crittografia TLS utilizzata per la connessione quando i messaggi vengono recapitati da e verso l'organizzazione di Office 365. Le connessioni stabilite con altri servizi di posta elettronica vengono crittografate tramite TLS quando TLS viene offerto da entrambi i lati. Il widget offre un'istantanea dell'ultima settimana di flusso di posta. Quando si fa clic su **Visualizza dettagli**, il riquadro a comparsa del **messaggio protetto in transito (tramite TLS)** Mostra la protezione TLS per i messaggi in entrata e in uscita dall'organizzazione.

![Riquadro a comparsa dei messaggi protetti in transito (tramite TLS) nel centro conformità & sicurezza di Office 365](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

Attualmente, TLS 1,2 è la versione più sicura di TLS offerta da Office 365. Spesso, è necessario conoscere la crittografia TLS utilizzata per i controlli di conformità. Probabilmente non si ha una relazione diretta con la maggior parte dei server di posta elettronica di origine e di destinazione (non è proprietaria e non è presente né Microsoft), pertanto non sono disponibili molte opzioni per migliorare la crittografia TLS utilizzata da tali server.

Tuttavia, è possibile utilizzare i [connettori](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) per garantire la migliore protezione TLS disponibile per i messaggi inviati tra i server di posta elettronica e Office 365. Il flusso di posta tra Office 365 e i server di posta elettronica personali o i server appartenenti ai propri partner è spesso più importante e sensibile rispetto ai messaggi normali, quindi si desidera applicare maggiore sicurezza e vigilanza ai messaggi. È possibile aggiornare o correggere i propri server di posta elettronica per migliorare la crittografia TLS utilizzata o rivolgersi ai propri partner per fare lo stesso. Il **rapporto del connettore** Visualizza sia il volume del flusso di posta che la crittografia TLS per i messaggi che utilizzano i connettori di Office 365.

## <a name="connector-report"></a>Rapporto connettore

Quando si fa clic sul collegamento del **rapporto connettore** dal riquadro a comparsa del **messaggio protetto in transito (tramite TLS)** , nel report vengono visualizzate informazioni sui messaggi inviati e ricevuti dall'organizzazione di Office 365 mediante i connettori. È possibile utilizzare i connettori tra i propri server di posta elettronica e Office 365 o i server del partner e Office 365. Il volume del messaggio per ogni connettore e la crittografia TLS per la connessione è disponibile. Inoltre, è anche possibile visualizzare i dati per i messaggi inviati o ricevuti in Office 365 senza utilizzare un connettore.

La visualizzazione del **flusso di posta** Mostra il volume dei messaggi attraverso il connettore per la settimana passata. È possibile modificare l'intervallo di date selezionando **filtro** in cui è possibile aumentare l'intervallo fino a un massimo di 30 giorni. La visualizzazione **tutto il flusso di posta** consente di visualizzare tutto il flusso di posta da e verso l'organizzazione di Office 365 tramite tutti i connettori. È possibile selezionare un connettore specifico in base al nome nel menu a discesa.

È possibile selezionare la visualizzazione **utilizzo TLS** dall'elenco a discesa per visualizzare la ripartizione della protezione TLS per i messaggi tramite il connettore. Analogamente alla relazione **panoramica sul rapporto TLS** , questa visualizzazione Mostra la percentuale delle diverse versioni di TLS. Per le connessioni TLS 1,0, è effettivamente necessario ottenere il server di posta elettronica o il server del partner aggiornato o risolto per evitare eventuali problemi quando il supporto di TLS 1,0 è finalmente deprecato in Office 365. Per ulteriori informazioni, vedere informazioni [di riferimento tecnico sulla crittografia in Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).

Insights punta ai connettori per attirare la vostra attenzione sui potenziali problemi di crittografia TLS per il connettore. Gli Insight sono: **No TLS è superiore al 25%** o **TLS 1,0 è superiore a 50%**. Se vengono visualizzate queste informazioni, è necessario esaminare i server di posta elettronica associati al connettore o contattare l'organizzazione partner.
