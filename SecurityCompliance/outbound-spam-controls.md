---
title: Controllo della posta indesiderata in uscita in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: Se l'organizzazione invia una quantità elevata di posta inviata in blocco contrassegnato come posta indesiderata, è possibile ottenere impedito l'invio di posta elettronica con Office 365. In questo articolo per ulteriori informazioni su del problema e operazioni su di esso.
ms.openlocfilehash: a18e584a260218a53494ef49dd2d7380a0a9a3f1
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769786"
---
# <a name="controlling-outbound-spam-in-office-365"></a>Controllo della posta indesiderata in uscita in Office 365

Da intraprendere gestione prendere in seria posta indesiderata in uscita dal momento che la nostra è un servizio condiviso.  Esistono molti clienti controllati da un pool condiviso di risorse, dove se un cliente riceve posta indesiderata in uscita, può diminuire la reputazione IP in uscita del servizio e influisce sulla distribuzione corretta di posta elettronica per gli altri utenti. È sleale per il cliente se il cliente B spams e un elenco di diversi blocklists IP di terze parti 3 l'indirizzo IP che viene utilizzato il metodo.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Operazioni che gli amministratori possono eseguire per controllare la posta indesiderata in uscita

- **Abilitare le notifiche quando un account è l'invio di posta indesiderata o arrestato**. Gli amministratori possono ottenere bcc'ed ogni volta che un messaggio è contrassegnato come posta indesiderata in uscita e inviato attraverso il pool ad alto rischio. Monitorando questa cassetta postale, gli amministratori possono rilevare se dispongono di un account compromesso della rete o se il filtro posta indesiderata viene inavvertitamente contrassegnare il messaggio di posta elettronica come posta indesiderata.  Sono disponibili ulteriori informazioni su come impostare il criterio della posta indesiderata in uscita [di seguito](configure-the-outbound-spam-policy.md).
 
- **Esaminare manualmente reclami posta indesiderata da 3rd provider di posta elettronica di terze parti**. Molti 3 ° servizi di posta elettronica di terze parti come Outlook.com, Yahoo! e AOL forniscono un ciclo di commenti e suggerimenti dove se tutti gli utenti nel proprio servizio contrassegna un messaggio di posta elettronica da questo servizio come posta indesiderata, il messaggio è incluso in un pacchetto e inviato a Microsoft per la revisione. Per ulteriori informazioni sul supporto di mittente per Outlook.com, fare clic [qui](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>Scopo della EOP per controllare la posta indesiderata in uscita 

1. **Separazione del traffico in uscita a pool distinti degli indirizzi IP**. Ogni messaggio inviato in uscita tramite il servizio clienti verrà esaminato per la posta indesiderata. Se il messaggio di posta indesiderata, vengono indirizzata tramite il pool di recapito rischio elevato. In questo pool IP contiene posta indesiderata e le notifiche di stato non recapitabile. Recapito per il destinatario non è garantito come molte terze parti non accetterà posta elettronica perché la qualità della posta elettronica genera.

Divisione in questo modo il traffico assicura che posta elettronica di qualità inferiore (spam, rapporti di mancato recapito backscatter) non trascinare verso il basso reputazione dei pool di posta elettronica in uscita normale. Pool ad alto rischio ha in genere reputazione bassa in molte ricevitori intorno a Internet, sebbene non sia universale. 

2. **Monitoraggio del protocollo IP reputazione**. Office 365 esegue una query diversi 3rd blocklists IP di terze parti e genera avvisi se uno dei nostri IP in uscita siano elencato nel loro. In questo modo di reagire con prontezza quando la posta indesiderata ha causato reputazione a peggiorare. Quando viene generato un avviso, è disponibile documentazione interna fonte illustrati i passaggi da eseguire per ottenere venga rimosso dall'elenco. 

3. **Disabilitazione degli account pericoloso quando inviano posta troppo contrassegnati come posta indesiderata**. Anche se è separare i nostri posta indesiderata e non in due pool differenti IP in uscita, l'account di posta elettronica non è possibile inviare la posta indesiderata per un tempo indefinito. È monitorare i cui account sono l'invio di posta indesiderata e se supera un limite riservato, l'account viene impedito l'invio di posta indesiderata.

Un singolo messaggio è contrassegnato come posta indesiderata può essere un errore di classificazione dal motore di posta indesiderata e noto anche come falso positivo. Si invia tramite il pool ad alto rischio per fornire la possibilità di passare in caso contrario. Tuttavia, un numero elevato di messaggi in una cornice di un'ora breve 24h indicativo del problema e quando si verifica che, si blocca l'account di inviare un messaggio di posta elettronica più. Sono disponibili diverse soglie esistenti per l'account di posta elettronica singoli anche come funzione di aggregazione per l'intero tenant.

4. **Disabilitazione degli account pericoloso quando inviano troppo posta elettronica in troppo breve un intervallo di tempo**. Oltre i limiti sopra che hanno l'aspetto di una proporzione dei messaggi contrassegnati come posta indesiderata, esistono limiti che bloccano l'account quando viene raggiunto un limite globale indipendentemente dal fatto che i messaggi vengono contrassegnati come posta indesiderata. Ragione che esiste questo limite è un account compromesso può inviare la posta indesiderata zero-day che non è stata eseguita dal filtro posta indesiderata. Poiché è difficile, se non Impossibile indicare in alcuni casi la differenza tra una campagna di mailing di massa legittima e una campagna di enormi posta indesiderata, questi limiti attivare per limitare i potenziali danni.

> [!NOTE]
> Per #3 e 4 #, è advertise non esatti limiti.  Si tratta di prevenire lo il sistema di gioco e per garantire che è possibile modificare i limiti di quando è necessario. I limiti sono sufficientemente elevato in modo che non verrà mai raggiunto un utente aziendale medio e sufficientemente bassa che contiene la maggior parte dei danni che un mittente può eseguire. 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Soluzioni alternative consigliate per i clienti che desiderano inviare una grande quantità di posta elettronica attraverso EOP in uscita

È difficile stabilire un equilibrio tra i clienti che desiderano inviare un volume elevato di posta elettronica e protezione del servizio da account compromesso ed emailers di massa con alle pratiche di acquisizione di una scarsa elenco. Anche il costo totale di destinazione in un blocco di terze parti 3rd indirizzi IP in uscita è superiore al blocco di un cliente di inviare posta elettronica in uscita. Come descritto in [Exchange Online Service Description](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits), utilizzo EOP per l'invio di posta elettronica in blocco non è un utilizzo del servizio ed è consentita solo singole "massimo sforzo". Per i clienti che si desidera inviare posta elettronica in blocco, si consiglia quanto segue:

r. **inviare la posta elettronica in blocco tramite i proprio locale nel server di posta elettronica**. Ciò significa che il cliente avrà gestire il proprio dell'infrastruttura di posta elettronica per questo tipo di messaggio di posta elettronica.

b. **emailer blocco parti di utilizzare un 3rd per inviare la comunicazione di massa**. Esistono diversi emailers di massa di terze parti la cui attività unicamente può inviare posta elettronica in blocco 3. Lavorano con clienti per garantire che dispongono di invio consigliate e dispongono di risorse dedicate per l'applicazione viene. 

La messaggistica, Mobile, Malware anti-parte di un gruppo di lavoro (MAAWG) consente di pubblicare il relativo elenco di appartenenza [di seguito](http://www.maawg.org/about/roster). Più provider di posta elettronica in blocco nell'elenco e sono noti come responsabili dei cittadini Internet. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Protezione anti-spoofing in Office 365](anti-spoofing-protection.md)

[Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md)
