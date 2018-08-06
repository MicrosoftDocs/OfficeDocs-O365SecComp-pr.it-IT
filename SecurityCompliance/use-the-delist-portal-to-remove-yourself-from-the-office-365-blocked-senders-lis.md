---
title: Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
description: Viene visualizzato un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Office 365? Se si ritiene di non dover ricevere tale messaggio di errore, è possibile utilizzare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365.
ms.openlocfilehash: 127b305cdb27cffadc7ad6a43a5d2db2440365ca
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026233"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365

Viene visualizzato un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Office 365? Se si ritiene di non dover ricevere tale messaggio di errore, è possibile utilizzare il portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365.
  
## <a name="what-is-the-office-365-blocked-senders-list"></a>Che cos'è l'elenco dei mittenti bloccati di Office 365?

Microsoft utilizza l'elenco dei mittenti bloccati per proteggere i propri clienti da posta indesiderata, spoofing e attacchi di phishing. L'indirizzo IP del server di posta degli utenti, ovvero l'indirizzo utilizzato dal proprio server di posta per l'identificazione su Internet, è stato contrassegnato come potenziale minaccia in Office 365 per qualche motivo particolare. Quando l'indirizzo IP viene aggiunto all'elenco, Office 365 impedisce tutte le ulteriori comunicazioni tra tale indirizzo e un cliente qualsiasi tramite i datacenter.
  
Gli utenti scoprono di essere stati aggiunti all'elenco quando ricevono una risposta a un messaggio di posta elettronica che include un errore simile a quanto segue:
  
550 5.7.606-649 accesso negato, vietata invio IP [ _indirizzo IP_]; Per richiedere la rimozione dall'elenco, visitare https://sender.office.com/ e seguire le istruzioni. Per ulteriori informazioni, vedere [rapporti di mancato recapito di posta elettronica in Office 365](http://go.microsoft.com/fwlink/?LinkID=526653).
  
_IP address_ è l'indirizzo IP del computer in cui è in esecuzione il server di posta. 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Per accedere al portale di esclusione di Office 365 e rimuoversi dall'elenco dei mittenti bloccati

1. In un browser Web, andare a [https://sender.office.com](https://sender.office.com).
    
2. Seguire le istruzioni visualizzate sulla pagina. Accertarsi di utilizzare l'indirizzo di posta elettronica al quale è stato recapitato il messaggio di errore e l'indirizzo IP specificato nel messaggio di errore. È possibile immettere solo un indirizzo di posta elettronica e un indirizzo IP per accesso.
    
3. Fare clic su **Invia**.
    
    Il portale invia un messaggio di posta elettronica all'indirizzo di posta elettronica che si fornisce. Messaggio di posta elettronica avrà un aspetto simile alla seguente: ![cattura di schermata del messaggio di posta elettronica ricevuto quando si invia una richiesta tramite il portale delist](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)
  
4. Fare clic sul collegamento di conferma nel messaggio di posta elettronica inviato all'utente dal portale di esclusione.
    
    In questo modo si torna al portale di esclusione.
    
5. Nel portale di esclusione, fare clic su **Escludi indirizzo IP dall'elenco**.
    
    Dopo la rimozione dell'indirizzo IP dall'elenco dei mittenti bloccati, i messaggi di posta elettronica dall'indirizzo IP verranno recapitati ai destinatari che utilizzano Office 365. Pertanto, assicurarsi che la posta elettronica inviata da tale indirizzo IP non sia offensiva o dannosa; in caso contrario, l'indirizzo IP verrà bloccato di nuovo.
    

