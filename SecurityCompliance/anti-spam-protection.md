---
title: Protezione dalla posta indesiderata in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: Informazioni sulle impostazioni di protezione da posta indesiderate e i filtri che sono contenute informazioni utili che impedire la posta indesiderata in Exchange Online e Office 365. Ricevere troppo posta indesiderata in Office 365? È possibile personalizzare il filtro da posta indesiderata e le impostazioni di criteri di protezione da posta indesiderata.
ms.openlocfilehash: 0a23ddd0610599bbd6478781c61e5e32b06726bc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29652271"
---
# <a name="office-365-email-anti-spam-protection"></a>Protezione dalla posta indesiderata in Office 365

Si desidera evitare troppo posta indesiderata in Office 365? È stata incorporata più filtri posta indesiderata nel servizio Office 365 o Exchange Online Protection (EOP) in modo che la posta elettronica è protetta dal momento in cui che viene visualizzato il primo messaggio. Per evitare la posta indesiderata in Office 365, è possibile modificare un'impostazione di protezione di gestione di un problema specifico all'interno dell'organizzazione, ad esempio si ricevono una quantità elevata di posta indesiderata da un mittente specifico, ad esempio, o in semplicemente fine regolare le impostazioni in modo che siano personalizzati per più adatte alle esigenze dell'organizzazione. A tale scopo, è possibile modificare le impostazioni di protezione da posta indesiderate in Office 365 Security &amp; centro conformità.
  
In questo articolo è destinato agli amministratori di Office 365. Se non si è un amministratore, ma si è un utente di Office 365 e che desiderano apprendere le modalità di gestione con la posta indesiderata che viene visualizzato, questo non è l'articolo che si sta cercando. Al contrario, se si utilizza Outlook per PC o Outlook per Mac, Usa [Panoramica del filtro per la posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Se si utilizza Outlook sul web, iniziare con [informazioni sulla posta indesiderata e phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Queste opzioni consentono di evitare la posta indesiderata in Office 365

 **Filtro connessioni.** Quando si utilizzano il filtro connessioni, Office 365 controlla la reputazione del mittente prima di consentire un messaggio di ottenere tramite. È possibile creare un elenco Consenti o un elenco dei mittenti attendibili, per assicurarsi che ogni messaggio viene inviato da un indirizzo IP specifico o un intervallo di indirizzi IP. È inoltre possibile creare un elenco di indirizzi IP da utilizzare per bloccare i messaggi, viene chiamati un elenco di blocco. Per ulteriori informazioni, vedere [Configure Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). Se si è interessati sulla posta indesiderata in Office 365, utilizzare il filtro connessioni per evitare la posta indesiderata.
  
Per i clienti che dispongono di Office 365 Enterprise E5 o hanno acquistato licenze avanzate Threat Protection (degli strumenti di analisi), il filtro connessioni viene utilizzato per business intelligence di spoofing per creare elenchi di mittenti attendibili che sono lo spoofing del dominio Consenti e blocca. Per ulteriori informazioni, vedere [riferimento alle informazioni sulla business intelligence di spoofing](https://go.microsoft.com/fwlink/?LinkID=735009).
  
 **Filtro posta indesiderata.** Office 365 controlla delle caratteristiche del messaggio coerente con la posta indesiderata tramite il filtro posta indesiderata. È possibile modificare le azioni per eseguire sui messaggi identificati come posta indesiderata e scegliere se si desidera filtrare i messaggi scritti in determinate lingue o inviati da determinati paesi o aree. È inoltre possibile attivare avanzate per posta indesiderata opzioni di filtro se si desidera utilizzare un approccio aggressivo filtro posta indesiderata. Inoltre, è possibile configurare le notifiche di posta indesiderata dell'utente finale per informare gli utenti quando i messaggi destinati a loro sono stati messi in quarantena invece. (L'invio di messaggi in quarantena è una delle operazioni configurabile). Queste notifiche agli utenti finali possono rilasciare falsi positivi e segnalarli a Microsoft per l'analisi. Per ulteriori informazioni, vedere [configurazione dei criteri di filtro posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=617147). Per contribuire a evitare la posta indesiderata in Office 365, utilizzare la posta indesiderata, se si è preoccupati troppo posta indesiderata in Office 365, utilizzare il filtro connessioni per evitare la posta indesiderata.
  
> [!NOTE]
> Per i clienti EOP autonomo: per impostazione predefinita, il filtro da posta indesiderata EOP invia messaggi di rilevamento posta indesiderata nella cartella posta indesiderata di ogni destinatario. Tuttavia, per assicurare che l'azione **Sposta il messaggio nella cartella posta indesiderata** funzionino con cassette postali locali, è necessario configurare due regole di trasporto di Exchange sui server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [verificare che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx). 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Informazioni aggiuntive se vengono visualizzati troppo posta indesiderata in Office 365

Nel seguente video viene fornita una panoramica della configurazione della posta indesiderata in EOP.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
Per ulteriori informazioni, vedere l'argomento [Configure criteri di filtro della posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=617147) .
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Controllare i messaggi in uscita per evitare la posta indesiderata in Office 365

 **Un filtro in uscita.** Office 365 consente inoltre di verificare che gli utenti non inviino posta indesiderata. Ad esempio computer dell'utente può ottenere contenere malware che ne determina la inviare messaggi di posta indesiderata, in modo creiamo difesa contro che ha chiamato *un filtro in uscita* . Non è possibile disattivare il filtro in uscita, ma è possibile configurare le impostazioni descritte in [configurare i criteri di posta indesiderata in uscita](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). Se si è preoccupati troppo posta indesiderata in Office 365, utilizzare il filtro in uscita per evitare la posta indesiderata in Exchange Online.
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Oltre a informazioni di base: ulteriori modi per evitare la posta indesiderata in Office 365

 **Regole del flusso di posta.** Se si desidera andare oltre il filtro posta indesiderata integrato e creare regole personalizzate che si basano sui criteri aziendali, le *[regole del flusso di posta elettronica](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*, denominati anche *le regole di trasporto*, sono un altro filtro che consentono di evitare la posta indesiderata in Office 365. Ad esempio, è possibile utilizzare le regole di flusso di posta elettronica per impostare il valore di (SCL) livello spam confidence per i messaggi che soddisfano le condizioni specifiche, come descritto in [utilizzare le regole di flusso di posta elettronica per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).
  
 **L'autenticazione di posta elettronica.** Le tecniche che utilizzano il sistema DNS (Domain Name) per aggiungere informazioni verificabili a messaggi di posta elettronica relative al mittente di un messaggio di posta elettronica vengono chiamate l'autenticazione di posta elettronica. Gli amministratori possono rendere più avanzate di Office 365 utilizzare questi metodi di autenticazione di posta elettronica:
  
- **Sender Policy Framework (SPF).** SPF consente di convalidare l'origine dei messaggi di posta elettronica per verificare l'indirizzo IP del mittente per il proprietario presunto del dominio di invio. Per una breve introduzione a SPF e per ottenere una configurazione rapidamente, vedere [impostare SPF in Office 365 per evitare attacchi di spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Per una più approfondita dei come Office 365 utilizza SPF o per le distribuzioni di risoluzione dei problemi o non standard, ad esempio le distribuzioni ibride, iniziare con [la modalità di Office 365 utilizza mittente Policy Framework (SPF) per impedire attacchi di spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).

- **DomainKeys identificato posta (DKIM).** DKIM consente di collegare una firma digitale a messaggi di posta elettronica nell'intestazione del messaggio di posta elettronica da inviare. Sistemi di posta elettronica ricevano della posta elettronica dal dominio utilizzano la firma digitale per determinare se posta elettronica in arrivo che ricevono è valido. Per informazioni su DKIM e Office 365, vedere [Utilizzo DKIM per convalidare la posta elettronica inviata dal dominio in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).

- **Autenticazione dei messaggi basati sul dominio, Reporting e conformità (DMARC).** Vengono fornite informazioni utili DMARC la ricezione di sistemi di posta elettronica determinano cosa fare con messaggi di errore verifiche SPF o DKIM e fornendo un altro livello di attendibilità per i partner di posta elettronica. Per informazioni sull'impostazione DMARC, vedere [Utilizzo DMARC per convalidare la posta elettronica in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Se si è interessati su posta indesiderata, phishing e spoofing in Office 365, utilizzare SPF, DKIM e DMARC insieme al fine di evitare la posta indesiderata e lo spoofing indesiderati.
  
 **Impostazioni gestito per l'utente finale.** Si sta cercando informazioni su come gli utenti finali possono gestire le proprie impostazioni della posta indesiderata, vedere [Panoramica del filtro per la posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=270065) (per gli utenti di Microsoft Outlook) o [fare riferimento alle informazioni sulla posta indesiderata e phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (per Outlook sugli utenti web). Se si sta utilizzando EOP per proteggere le cassette postali locali, assicurarsi di utilizzare la sincronizzazione delle directory per assicurarsi che queste impostazioni vengono sincronizzate con il servizio. Per ulteriori informazioni sull'impostazione di sincronizzazione della directory, vedere "Utilizzare la sincronizzazione delle directory per gestire gli utenti di posta" in [Gestione utenti di posta in EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Blog: Perché di posta indesiderata e phishing visualizzato tramite Office 365?](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[Domande frequenti sulla protezione da posta indesiderata](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](prevent-email-from-being-marked-as-spam-0.md)
  
[Come impostare il filtro consente di bloccare i messaggi di posta indesiderata antispam di Office 365](block-email-spam-to-prevent-false-negatives.md)
  
[Che cos'è la differenza tra posta indesiderata e posta elettronica in blocco?](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[Intestazioni messaggi della protezione da posta indesiderata](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[Backscatter recapito ed EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a>Altre risorse

[Ottenere assistenza dai forum della community di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[Amministratori: Accedere e creare una richiesta di servizio](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[Amministratori: Contattare il supporto](https://go.microsoft.com/fwlink/p/?LinkID=518322)
