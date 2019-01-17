---
title: Flusso di posta in ingresso e in uscita
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Gli amministratori possono venire a conoscenza l'uscita e widget del flusso di posta in ingresso nel dashboard di flusso della posta in & la protezione di Office 365 centro conformità.
ms.openlocfilehash: 57792c0347490b40f97a8b92945a9c809484ba4f
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685500"
---
# <a name="outbound-and-inbound-mail-flow"></a>Flusso di posta in ingresso e in uscita

Il **flusso di posta in ingresso e in uscita** widget combina le informazioni dal **Connettore di Report** e il precedente **TLS panoramica Report** in un unico sito.

![Il rapporto di flusso della posta in uscita e in ingresso nel dashboard di flusso della posta in & la protezione di Office 365 centro conformità](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

Le informazioni contenute in widget sono correlate a connettori e la protezione dei messaggi TLS in Office 365. Per ulteriori informazioni, vedere questi argomenti:

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Come viene utilizzato TLS per proteggere il traffico della posta elettronica in Office 365](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>Messaggio protetto in transito (tramite TLS)

Widget **flusso di posta in ingresso e in uscita** consente di visualizzare la crittografia TLS utilizzato per la connessione quando i messaggi vengono recapitati a e dall'organizzazione Office 365. Le connessioni che vengono create con altri servizi di posta elettronica vengono crittografate tramite TLS quando TLS è disponibile per entrambi i lati. Widget offre uno snapshot dell'ultima settimana del flusso di posta. Quando si fa clic su **Visualizza dettagli**, la comparsa **messaggio protetto in transito (tramite TLS)** Mostra la protezione TLS per i messaggi di immissione e in uscita dall'organizzazione.

![I messaggi protetti in transito (tramite TLS) menu mobile & la protezione di Office 365 centro conformità](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

Attualmente, 1.2 TLS è la versione più sicura di TLS è disponibile per Office 365. Spesso, è necessario conoscere la crittografia TLS utilizzato per i controlli di conformità. Probabilmente non si dispone di una relazione diretta con la maggior parte dei server di origine e destinazione posta elettronica (non si è proprietari e non consente Microsoft), in modo che non sono disponibili molte opzioni per migliorare la crittografia TLS utilizzato da tali server.

Tuttavia, è possibile utilizzare [i connettori](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) per assicurare l'ottimale disponibili TLS protezione per i messaggi inviati tra i server di posta elettronica e Office 365. Flusso di posta tra Office 365 e il proprio server di posta elettronica o il server che appartengono ai partner è spesso più importanti e importanti di messaggi normali, dunque è necessario applicare maggiore sicurezza e resta a tali messaggi. È possibile aggiornare o correggere i propri server di posta elettronica per migliorare la crittografia TLS è utilizzata o raggiunga i partner per eseguire la stessa operazione. Il **Connettore di Report** vengono visualizzati sia volume del flusso di posta elettronica e la crittografia TLS per i messaggi che utilizzano i connettori di Office 365.

## <a name="connector-report"></a>Report di connettore

Quando si fa clic sul collegamento **Connettore Report** dall'elemento libero **messaggio protetto in transito (tramite TLS)** , il report vengono visualizzate informazioni sui messaggi vengono recapitati da e verso l'organizzazione di Office 365 utilizzando i connettori. Utilizzare i connettori tra i server di posta elettronica e Office 365 o del partner server e Office 365. Il volume di messaggio per ciascun connettore e la crittografia TLS per la connessione è disponibile. Inoltre, è inoltre possibile visualizzare i dati per i messaggi che sono stati inviati o ricevuti in Office 365 senza utilizzare un connettore.

Il **Flusso di posta** di visualizzare il volume dei messaggi attraverso il connettore per l'ultima settimana. È possibile modificare l'intervallo di date selezionando **filtro** dove è possibile aumentare l'intervallo a un massimo di 30 giorni. Visualizza **Tutto il flusso di posta elettronica** viene visualizzato flusso di tutta la posta da e verso l'organizzazione Office 365 a tutti i connettori. È possibile selezionare uno specifico connettore in base al nome nel menu a discesa.

È possibile selezionare la visualizzazione **uso TLS** discesa verso il basso per vedere la suddivisione di protezione TLS per i messaggi attraverso il connettore. Come con **TLS Panoramica** rapporto consente di visualizzare la percentuale di diverse versioni TLS. Per le connessioni TLS 1.0, è effettivamente necessario ottenere il server di posta elettronica o server dei partner aggiornati o uno spazio evitare eventuali problemi durante il supporto TLS 1.0 alla fine è obsoleto in Office 365. Per ulteriori informazioni, vedere [informazioni di riferimento tecniche sulla crittografia in Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).

Approfondimenti scegliere connectors per facilitare il disegnare attenzione ai potenziali problemi di crittografia TLS per il connettore. Le informazioni vengono: **No TLS è superiore al 25%** o **TLS 1.0 è superiore al 50%**. Se viene visualizzata queste considerazioni, è necessario analizzare i server di posta elettronica che sono associato il connettore o raggiungono la propria organizzazione partner.
