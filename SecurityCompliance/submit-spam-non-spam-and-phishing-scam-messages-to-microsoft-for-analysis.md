---
title: Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
description: "È possibile inviare messaggi false negativo e falso positivo della posta indesiderata a Microsoft per l'analisi. "
ms.openlocfilehash: 1ae33fc7208ab679b7eeb148007bb3b676533e55
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026423"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi

Può essere frustrante quando gli utenti nell'organizzazione ricevono messaggi di posta indesiderata (spam) o messaggi di phishing phishing nella posta in arrivo o che non riceveranno un messaggio di posta elettronica legittimi dal momento che venga contrassegnato come posta indesiderata. È costantemente stiamo localizzatore il filtro da posta indesiderata per ottenere una maggiore precisione. Gli utenti possano consentono di questo processo per l'invio di messaggi false negativo e falso positivo della posta indesiderata a Microsoft per l'analisi. Un negativo"false" è un messaggio di posta indesiderata che avrebbe dovuto essere ma non è stato identificato come posta indesiderata. "Falso positivo" è un messaggio di posta elettronica legittimi erroneamente identificato come posta indesiderata. 
  
> [!NOTE]
> A causa del numero elevato di invio che viene visualizzato, si potrebbe non essere in grado di rispondere a tutte le richieste per l'analisi. 
  
## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Inviare messaggi di posta indesiderata o tentativi di phishing che hanno superato i filtri posta indesiderata
<a name="sectionSection0"> </a>

Se si riceve un messaggio in cui è passato attraverso la posta indesiderata che applica un filtro e deve essere classificato come posta indesiderata o un messaggio di phishing, è possibile inviare il messaggio "false negativo" ai team di analisi della posta indesiderata di Microsoft e Microsoft Phishing Analysis, come appropriato. Analisti verranno esaminare il messaggio e aggiungere filtri a livello di servizio se soddisfa i criteri di classificazione. 
  
Per ulteriori impostazioni di posta indesiderata che si applicano a tutta l'organizzazione, vedere [bloccare lo spamming di posta elettronica con il filtro posta indesiderata di Office 365 per evitare problemi negativi false](https://go.microsoft.com/fwlink/p/?LinkId=534225). In questo articolo è contenuti suggerimenti per evitare falsi negativi.
  
È possibile inviare messaggi di posta indesiderata nei modi seguenti:
  
- Per Outlook e Outlook per gli utenti il web, utilizzare il componente aggiuntivo di report per Microsoft Outlook. Per informazioni su come installare e utilizzare questo strumento, vedere [abilitare il componente aggiuntivo di report](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676). 
        
- È inoltre possibile utilizzare posta elettronica per inviare messaggi a Microsoft che deve essere classificato come posta indesiderata o tentativi di phishing, come descritto nella procedura seguente.
    
### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>Inviare messaggi di posta indesiderata o tentativi di phishing a Microsoft
<a name="Useemailtosubmitjunkspamorphishingscammessages"> </a>

Per inviare messaggi di posta indesiderata o tentativi di phishing a Microsoft:
  
1. Creare un messaggio di posta elettronica vuoto.
    
2. Indirizzare il messaggio al team Microsoft che esamina i messaggi, come indicato di seguito: 
    
  - Per i messaggi indesiderati: junk@office365.microsoft.com
    
  - Per i messaggi di phishing phishing: phish@office365.microsoft.com
    
3. Copiare e incollare il messaggio di posta indesiderata o phishing phishing del nuovo messaggio come allegato. 
    
    > [!NOTE]
    > È possibile collegare più messaggi per il nuovo messaggio. Verificare che tutti i messaggi sono dello stesso tipo, ovvero i messaggi di phishing phishing o messaggi di posta elettronica. > Lasciare vuoto il corpo del nuovo messaggio. 
  
4. Fare clic su **Invia**.
    
## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Inviare messaggi contrassegnati come posta indesiderata ma che dovrebbero essere autorizzati
<a name="sectionSection1"> </a>

Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviare il messaggio "falso positivo" al Team di analisi della posta indesiderata di Microsoft. Analisti verranno valutare e analizzare il messaggio. In base ai risultati dell'analisi, le regole di filtro dei contenuti da posta indesiderata a livello di servizio possono essere regolate per consentire il messaggio attraverso.
  
Gli amministratori possono esaminare ulteriori informazioni sulle impostazioni della posta indesiderata che si applica a un'intera organizzazione. Vedere [per contribuire a garantire che un messaggio non è contrassegnato come posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=534224). Queste informazioni sono utile se si dispone di controllo a livello di amministratore e si desidera impedire falsi positivi.
  
È possibile inviare messaggi non di posta indesiderata nei modi seguenti:
  
- Se si utilizza l'azione **spostare il messaggio nella cartella posta indesiderata** quando si configurano i filtri del contenuto (si tratta dell'azione predefinita), gli utenti possono rilasciare messaggi falsi positivi nella propria cartella Outlook OWA posta indesiderata o. 
    
  - Gli utenti di Outlook è possono rilasciare messaggi falsi positivi tramite l'opzione di menu **Non indesiderato** pulsante destro del mouse. Tuttavia, si deve inviare il messaggio a Microsoft tramite posta elettronica, come illustrato nella procedura in questo articolo. 
    
  - Gli utenti di OWA possono rilasciare messaggi falsi positivi e le invia a Microsoft per l'analisi dell'utilizzo dell'azione di **contrassegnare come non indesiderato** . Per ulteriori informazioni su come eseguire questa operazione, vedere [la posta indesiderata di Report e i tentativi di phishing in Outlook sul web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
    
- Se si utilizza l'azione di **messaggi in quarantena** invece dell'azione **spostare il messaggio nella cartella posta indesiderata** quando si configurano i filtri del contenuto: 
    
  - Gli amministratori possono rilasciare i messaggi di quarantena della posta indesiderata e segnalarli come falsi positivi dall'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come amministratore](find-and-release-quarantined-messages-as-an-administrator.md).
    
  - Gli utenti possono rilasciare i propri messaggi nella quarantena della posta indesiderata e segnalarli come falsi positivi tramite i canali seguenti: 
    
  - Interfaccia utente EAC. Per ulteriori informazioni, vedere [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
    
  - Messaggi di notifica di posta indesiderata utente finale (se abilitati dall'amministratore). 
    
- È inoltre possibile utilizzare posta elettronica per inviare messaggi a Microsoft che non devono essere classificate come posta indesiderata. A tale scopo, accertarsi di utilizzare i passaggi nella procedura seguente.
    
### <a name="use-email-to-submit-false-positive-messages"></a>Utilizzo della posta elettronica per inviare messaggi falsi positivi

Utilizzare la stessa procedura come descritto in "[utilizzo della posta elettronica per inviare posta indesiderata (spam) o messaggi di phishing phishing a Microsoft ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md#Useemailtosubmitjunkspamorphishingscammessages)", ma inviare il messaggio a not_junk@office365.microsoft.com.
  
## <a name="spam-evaluation-and-rules-deployment"></a>Distribuzione di valutazione e le regole della posta indesiderata
<a name="sectionSection2"> </a>

Il team di analisi della posta indesiderata vengono esaminati i messaggi di invio e modifica filtro da posta indesiderata per impedire futuri della posta indesiderata. Di conseguenza, posta indesiderata di Office 365 Filtra areconstantly notte. Tutti gli elementi inviati vengono valutati a livello di tutta la rete. Ricezioni falsi positivi vengono esaminate e valutate per la prima regolazione regola possibili consentire i messaggi futuri attraverso i filtri posta indesiderata. Di conseguenza, la notifica del servizio dei falsi positivi e falsi negativi (non filtrato spam) è utile e tutti i clienti che utilizzano la rete globale. Il team di posta indesiderata esamina gli indicatori all'interno di ogni messaggio inviato, ad esempio le operazioni seguenti:
  
- Indirizzo mittente
    
- Indirizzo IP di invio
    
- Parole chiave
    
- Frasi
    
- Frequenza di trasmissione
    
- Altre tendenze e modelli
    
Dopo la revisione queste informazioni, il team di posta indesiderata potrebbe apportare modifiche a livelli di filtraggio della posta indesiderata del servizio. Per ulteriori informazioni relative al team di posta indesiderata, è possibile guardare il video solo in inglese seguente:
  
[Team di Microsoft Exchange Spam video](https://youtu.be/-TpX_-GMC7o?hd=1)
  
La valutazione della posta indesiderata è un processo continuo applicabile a prescindere dal set di caratteri o della lingua di origine. Dal momento che un messaggio di posta indesiderata può essere vago o non contenere testo nell'oggetto o nel corpo, il team della posta indesiderata si basa su altre caratteristiche del messaggio per eseguire il filtraggio. Ciò significa che dopo che il team ha contrassegnato un determinato messaggio come posta indesiderata e ha apportato le necessarie modifiche alla base di regole, il messaggio viene bloccato finché le relative caratteristiche non hanno subito modifiche sufficienti ad evitare i filtri. Nuove regole per la posta indesiderata vengono sviluppate continuamente. I tempi necessari per lo sviluppo di nuove regole o l'analisi dei messaggi inviati possono variare a seconda della quantità e della qualità degli invii. Poiché le nuove regole della posta indesiderata vengono impostate globalmente per tutti gli utenti, non tutti i singoli invii di posta indesiderata determineranno la creazione di una nuova regola.
   
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection4"> </a>

[Protezione antispam e antimalware](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)
  
[Come assicurarsi che un messaggio non venga contrassegnato come indesiderato](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

