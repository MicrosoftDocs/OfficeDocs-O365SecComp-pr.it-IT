---
title: Delle conoscenze di business intelligence spoofing procedura dettagliata
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: Vedere come funziona delle conoscenze nuovo intelligence spoofing.
ms.openlocfilehash: ca9c4ae6f2d65ef2700a2e02acd5b4f1dfbfe903
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22596095"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Procedura dettagliata: spoofing intelligence informative

Utilizzando informative spoofing Intelligence, è possibile determinare rapidamente i mittenti legittimo inviano che non autenticati di posta elettronica. Che possono inviare messaggi di spoofing, è possibile ridurre il rischio di eventuali falsi positivi continui agli utenti.
  
Inoltre, è possibile utilizzare monitor di Business Intelligence di spoofing e gestione di coppie di dominio consentite per fornire un ulteriore livello di sicurezza e impedire che i messaggi non sicuri che arrivano nella propria organizzazione.
  
È possibile utilizzare delle conoscenze di business intelligence spoofing in sicurezza &amp; centro conformità se è stato assegnato l'account di lavoro o della scuola amministratore globale di Office 365, amministratore della sicurezza o le autorizzazioni di lettura di sicurezza. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
  
Se non si conosce [report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md), possono essere utili per visualizzare come è possibile passare da un dashboard a delle conoscenze e azioni consigliate.
  
È possibile visualizzare delle conoscenze intelligence spoofing da più di un dashboard in sicurezza &amp; centro conformità. Indipendentemente dal dashboard di cui sta osservando delle conoscenze fornisce i dettagli stessi e consente di eseguire rapidamente le stesse attività.
  
Questa è una delle diverse procedure dettagliate per la sicurezza &amp; centro conformità. Per informazioni sull'esplorazione di report e sui concetti, vedere le procedure dettagliate nella sezione su argomenti correlati.
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Guida per delle conoscenze intelligence spoofing nella protezione &amp; centro conformità

1. Per iniziare, è necessario [passare a sicurezza &amp; centro conformità](go-to-the-securitycompliance-center.md).
    
2. In sicurezza &amp; centro conformità, Vai alla **Gestione delle minacce** \> **Dashboard.**
    
3. Nella riga **sui concetti** , cercare delle conoscenze di business intelligence spoofing. Se è stata abilitata intelligence spoofing, sarà il diritto di informative **Spoofed domini che non è riuscita l'autenticazione degli ultimi 30 giorni**. Se non sono abilitate spoofing protezione, quindi delle conoscenze richiederà a tale scopo, utilizzare il titolo **Abilita protezione spoofing**. 
    
## <a name="about-the-insight-on-the-dashboard"></a>Su conoscenze nel dashboard di

Delle conoscenze nel dashboard di vengono visualizzate informazioni simile al seguente.
  
![Cattura di schermata di analisi di simulazione business intelligence](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Tali informazioni approfondite prevede due modalità:
  
 **Modalità delle conoscenze**. Se si dispone di tutti i criteri spoofing abilitato, quindi delle conoscenze Mostra messaggi quanti hanno subiti la funzionalità di business intelligence spoofing negli ultimi 30 giorni. 
  
 **Se modalità**. Se non è abilitato alcun criterio spoofing, quindi delle conoscenze mostra quanti messaggi *sarebbe* sono stati influenzati dalla funzionalità di business intelligence spoofing negli ultimi 30 giorni. 
  
In entrambi i casi, i domini falsificati visualizzati le informazioni sono suddivisi in due categorie. le coppie di dominio sospetti e coppie di dominio non sospetti. Queste categorie sono ulteriormente suddivise in tre diversi bucket per consentirne la verifica. 
  
Una *coppia di dominio* è una combinazione del "da:" indirizzo e l'infrastruttura di invio. 
  
- L'indirizzo "Da" è l'indirizzo visualizzato come indirizzo da per l'applicazione di posta elettronica. Questo indirizzo identifica l'autore del messaggio di posta elettronica. Vale a dire la cassetta postale della persona o del sistema responsabile della scrittura del messaggio. Questo è detto anche indirizzo 5322.From.
    
- L'invio dell'infrastruttura, o del mittente, è il dominio dell'organizzazione del record PTR dell'indirizzo IP del mittente. Se l'indirizzo IP del mittente Nessun record PTR, allora il mittente è identificato dall'indirizzo IP del mittente con il 255.255.255.0 subnet mask nella notazione CIDR (/ 24). Ad esempio, se l'indirizzo IP 192.168.100.100 l'indirizzo IP completo del mittente è 192.168.100.100/24.
    
 **Le coppie di dominio sospetti** includono: 
  
- **Spoofing confidenza elevata**. Office 365 ricevuto sicuro segnala che questi domini sono potenzialmente dannoso, basati su modelli di invio cronologici e punteggio reputazione di domini. Office 365 è estremamente sicuri spoofing di domini e che i messaggi inviati da questi domini sono meno probabilità di essere valido. 
    
- **Spoofing confidenza intermedie**. Office 365 ricevuto moderato segnala che questi domini sono potenzialmente dannoso, basati su modelli di invio cronologiche e il punteggio di reputazione di domini. Office 365 è medio la certezza che i domini vengono spoofing e che i messaggi inviati da questi domini sono legittimi. In questo bucket ha maggiori opportunità di contenente falsi positivi (FPs) di intervallo di confidenza elevata spoofing. 
    
 **Le coppie di dominio sospetti non** includere **soccorsi spoofing**. Spoofing recuperato sono i domini che hanno non è riuscita le verifiche di autenticazione esplicite ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) ma superato i controlli di autenticazione estesa. Di conseguenza, Office 365 ha recuperato telefonica per conto dell'utente e alla posta è stata eseguita alcuna azione anti-spoofing. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sulle coppie di dominio sospetti da conoscenze di business intelligence spoofing

1. Nella comprensione di business intelligence spoofing, fare clic su una delle coppie di dominio (elevate, medio o recuperate).
  
Verrà visualizzata la pagina **Delle conoscenze di Business Intelligence di simulazione** con un elenco di mittenti attendibili che sono l'invio dei messaggi non autenticati nell'organizzazione. Le informazioni contenute in questa pagina consentono di determinare se i messaggi di spoofing sono autorizzati o non o se è necessario eseguire ulteriori azioni. È possibile ordinare le informazioni dal numero dei messaggi, la data che di spoofing ultimo è stato rilevato, e altro ancora. Fare clic le intestazioni di colonna, ad esempio **messaggio contare** o **ultima indicato**, ad esempio. 
    
2. Selezionare un elemento nella tabella per aprire un riquadro dei dettagli che contiene informazioni dettagliate sulla coppia di dominio, inclusi il motivo per cui viene intercettata questo, cosa è necessario eseguire, un riepilogo di dominio, i dati WhoIs sul mittente e messaggi di posta elettronica simile finora nel tenant dello stesso mittente. Da qui è possibile aggiungere o rimuovere la coppia di dominio dall'elenco Mittenti attendibili **AllowedToSpoof** . 
  
![Cattura di schermata del dominio nel riquadro dei dettagli delle conoscenze intelligence spoofing](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Aggiungere o rimuovere un dominio dall'elenco Mittenti attendibili AllowedToSpoof

Aggiungere o rimuovere un dominio dall'elenco Mittenti attendibili AllowedToSpoof durante la revisione due il dominio nel riquadro dei dettagli delle conoscenze di business intelligence spoofing. È sufficiente impostare di conseguenza attiva o disattiva.
  
Ciò consente di modificare la combinazione di coppia di dominio univoco del dominio spoofing e l'infrastruttura di invio e non fornisce la copertura per l'intero dominio spoofing o l'infrastruttura di invio in isolamento. Ad esempio, se si aggiunge la seguente coppia di dominio per il mittente 'AllowedToSpoof' elenco Consenti: *Spoofing dominio* "gmail.com" e *L'invio di infrastruttura* "tms *. mx.com",* quindi solo la posta dalla coppia tale dominio sarà consentita effettuare lo spoofing. Altri mittenti si tenta di effettuare lo spoofing "gmail.com" e altri domini che tentano di "tms.mx.com" lo spoofing continuerà a essere protetti dalle intelligence spoofing. 
  
## <a name="related-topics"></a>Argomenti correlati

[Ulteriori informazioni su spoof intelligence](learn-about-spoof-intelligence.md)
  
[Protezione anti-spoofing in Office 365](anti-spoofing-protection.md)
  
[Istruzioni dettagliate: da una dashboard ad un approfondimento](from-a-dashboard-to-an-insight.md)
  
[Istruzioni dettagliate: da un report dettagliato ad un approfondimento](from-a-detailed-report-to-an-insight.md)
  
[Istruzioni dettagliate: da un approfondimento ad un report dettagliato](from-an-insight-to-a-detailed-report.md)
  

