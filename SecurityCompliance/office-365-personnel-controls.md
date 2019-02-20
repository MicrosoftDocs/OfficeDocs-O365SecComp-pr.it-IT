---
title: Controlli del personale di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Riepilogo: Panoramica delle procedure di screening del personale Microsoft per Office 365.'
ms.openlocfilehash: 126be117c790e4d8fc0328ee2dab6b97d516ab88
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091078"
---
# <a name="office-365-personnel-controls"></a>Controlli del personale di Office 365 

Lo screening del personale, che è il processo di revisione e convalida del comportamento e dello stato del passato di una persona, è un importante controllo di attenuazione per impedire il compromesso di servizio di Office 365. Anche se il comportamento passato non è un fattore predittivo perfetto del comportamento futuro di una persona, contribuisce all'identificazione di potenziali attori cattivi. Lo standard di screening del personale Microsoft si applica a tutti i dipendenti Microsoft, gli stagisti e il personale contingente coinvolti nello sviluppo, nel funzionamento o nella distribuzione dei servizi online ai clienti cloud governativi o commerciali. Gli standard di screening per gli ambienti cloud nazionali che non sono gestiti da Microsoft sono definiti dal personale dei partner operativi per ogni ambiente specifico.

## <a name="microsofts-personnel-screening-standard"></a>Standard di screening del personale Microsoft

Le procedure di screening del personale Microsoft per Office 365 sono allineate con i controlli di Microsoft Corporate Standards e National Institute of Standards and Technology (NIST) per lo screening del personale. Gli addetti Microsoft che richiedono l'accesso ai seguenti elementi sono soggetti alla norma di screening del personale Microsoft:
- Accesso fisico ai datacenter, alle coesistenze, alle sale protette, alle gabbie, ai server rack o ai siti perimetrali che forniscono l'infrastruttura che supporta i servizi online per i clienti governativi o commerciali del cloud.
- Accesso logico ai dati dei clienti cloud governativi o commerciali forniti tramite ambienti gestiti specifici.
    - Accesso alla gestione della rete ai dispositivi e ai servizi che trasportano o archiviano i dati dei clienti del cloud governativo o commerciale.

Gli eventi specifici relativi al personale che attivano i requisiti di screening includono:
- Nuovo personale Microsoft inserito nei ruoli in cui la selezione è un requisito definito.
- Personale Microsoft interno che trasferisce o trasferisce un ruolo esistente che attualmente include la schermatura come requisito definito.
- Ruoli esistenti che modificano l'ambito per includere lo screening come requisito definito.

## <a name="screening-enforcement-criteria"></a>Criteri di applicazione della schermatura

Per garantire che solo il personale autorizzato abbia accesso ai dati dei clienti o agli ambienti che richiedono la selezione, si applicano i criteri di applicazione seguenti:

**Solo ambienti cloud degli Stati Uniti**:
- L'accesso ai dati dei clienti o agli ambienti che richiedono la selezione deve essere consentito solo dopo il completamento dell'aggiudicazione e vengono passati i requisiti di screening.
- Il personale Microsoft che non richiede più l'accesso ai dati dei clienti o agli ambienti correlati deve avere accesso rimosso al momento di lasciare Microsoft o passare a un nuovo ruolo.
- Il personale Microsoft deve lasciare le smart card con gestione delle schermate dell'ambiente prima di lasciare gli Stati Uniti.

**Ambienti cloud nazionali**:
- L'operatore di terze parti o il personale trustee dei dati è responsabile della gestione e dell'applicazione dell'accesso per gli ambienti cloud nazionali.

Negli ambienti Microsoft Cloud Services, Access è limitato in base al ruolo di una persona e al tipo di dati coinvolti, come descritto nella tabella seguente. Non è consentito l'accesso ai dati dei clienti all'interno di un cloud degli Stati Uniti in un sito personale qualificato o non qualificato fisicamente all'esterno degli Stati Uniti. L'accesso agli ambienti cloud nazionali è limitato in modo che il personale Microsoft non disponga di accesso tecnico ai dati dei clienti, o sistemi che contengono dati dei clienti, senza l'approvazione da parte dell'operatore di terze parti o del trustee dei dati.

| Ruolo | Accesso ai dati dei clienti | Accesso ai dati di sistema |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|---------------------------------|
| Personale qualificato che si trova fisicamente negli Stati Uniti | Consentito | Consentito |
| Personale qualificato che si trova fisicamente all'esterno degli Stati Uniti | Non conSentita | Consentito |
| International Exception Access for Microsoft staff – Abilita l'accesso logico per il personale Microsoft che non risiede nel paese in cui il governo o i dati dei clienti commerciali sono a riposo | Non conSentita | Consentito |
| Personale non qualificato (personale non sottoposto a screening che richiede una scorta da personale qualificato) | Consentito con autorizzazione | Consentito con supervisione Escort |


## <a name="microsoft-pre-employment-screening"></a>Screening preimpiego Microsoft

Laddove la legge locale lo consente, il dipartimento di sicurezza globale di Microsoft conduce lo screening di preimpiego. Si tratta di un'analisi di sfondo formale che include i criteri seguenti:
- Un controllo (ad esempio, per completezza e accuratezza) del curriculum del richiedente
- Conferma dei diplomi accademici e professionali
- Indagini su eventuali perdite di credenziali professionali
- Verifica degli ultimi tre datori di lavoro
- Un controllo dei record di polizia per la convinzione del reato
- Conferma dell'identità da un'identificazione emessa dal governo
- Verifica del credito, se appropriato

Potrebbe essere necessario eseguire il rescreening periodico e/o ulteriori controlli in background per alcuni ruoli di gestione, sicurezza o di altro genere, tra cui i dipendenti basati su Stati Uniti nei ruoli che richiedono l'accesso ai dati dei clienti. Per il personale contingente, il contratto con terze parti specifica i requisiti di Microsoft per la selezione che devono essere eseguiti da terze parti. Per i controlli in background, la società di terze parti è responsabile di fornire alla verifica Microsoft che è stato eseguito un controllo in background. I risultati del controllo dei precedenti vengono in genere ricevuti tramite posta elettronica dal reparto risorse umane di terze parti. I dipendenti internazionali del personale contrattuale possono essere esonerati dal processo di screening in background a causa di leggi nei paesi che proibiscono i controlli in background.

## <a name="microsoft-employment-screening"></a>Screening di Microsoft Employment
Dal 2004, Microsoft ha richiesto agli utenti di passare uno schermo di sette anni di fedina penale per reati e reati, e di verificare la loro storia dell'istruzione e dell'occupazione, come parte dello screening preoccupazionale negli Stati Uniti per i dipendenti e gli stagisti.

Negli Stati Uniti, prima di assegnare qualsiasi dipendente Microsoft o un subappaltatore assegnato a Microsoft per fornire servizi correlati a Office 365, Microsoft condurrà e indurrà il suo subappaltatore a eseguire un controllo dei precedenti costituito da una sicurezza sociale traccia dei numeri e controllo dei precedenti penali. I dati provenienti da questo controllo di sfondo vengono utilizzati come fattore nella decisione di assunzione. Il controllo di fedina penale include un reato di sette anni e un controllo dei precedenti penali nei registri federali, statali e della contea (se applicabile).

Come condizione di impiego, al momento del noleggio, tutti i dipendenti Microsoft sono tenuti a firmare contratti di riservatezza e non divulgazione e a verificare di aver esaminato il manuale dei dipendenti Microsoft.

## <a name="microsoft-cloud-background-check"></a>Controllo del background di Microsoft Cloud
È necessario un controllo dei precedenti del cloud di Microsoft affinché i candidati vengano noleggiati come dipendenti che forniscono servizi correlati a Office 365 negli Stati Uniti. Gli impiegati Microsoft negli Stati Uniti con accesso ai dati dei clienti devono seguire il processo di controllo dei precedenti di Microsoft Cloud, che è necessario per tutti i servizi di Office 365. Al di fuori degli Stati Uniti, il processo varia. Ad esempio, il cloud Microsoft per la Germania utilizza un modello di approvazione del trustee dei dati, che è stato creato per garantire che il trustee dei dati (società tedesca) e non Microsoft sia in grado di controllare l'accesso ai dati dei clienti. Il cloud Microsoft in Germania viene recapitato dai data center in Germania e i centri operativi (OC) contenenti il personale tecnico del trustee dei dati sono anche in Germania. Sia il datacenter sia le strutture OC sono gestite, gestite e controllate dal trustee dei dati.

Nella tabella seguente sono elencati i controlli eseguiti come parte del controllo dei precedenti del cloud di Microsoft.

| Screening | Description |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ricerca del numero di preVidenza sociale | Verifica che il numero di preVidenza sociale fornito sia valido. |
| Controllo di precedenti penali | I record penali di sette anni controllano reati di reato e reato allo stato, alla contea e ai livelli locali e, a seconda dei casi, a livello federale. |
| Elenco di controllo delle risorse esterne di Office | Dipartimento del Tesoro elenco di persone e organizzazioni con cui non è consentito ai cittadini degli Stati Uniti e ai residenti permanenti di svolgere attività commerciali. |
| Bureau of Industry and Security List | Elenco del dipartimento di commercio delle persone e degli enti esclusi dall'attività di esportazione. |
| Office of Defense Trade Controls Debarred Persons List (*Aggiunta il 1 ° luglio 2010*) | Dipartimento di stato elenco delle persone e degli enti esclusi dall'impegno nelle attività di esportazione relative al settore della difesa. |


I risultati del controllo dei precedenti cloud di Microsoft sono archiviati nel database dei dipendenti, che è connesso ai sistemi di controllo di accesso ai datacenter. Se il controllo dei precedenti del cloud di Microsoft scade e il dipendente non lo rinnova, l'accesso ai servizi di Office 365 è revocato e non è più disponibile finché non viene completato di nuovo il controllo dei precedenti di Microsoft Cloud. Quando la relazione di lavoro con Microsoft termina, qualsiasi accesso datacenter esistente viene immediatamente revocato.

La cittadinanza degli Stati Uniti è verificata per tutti i dipendenti con accesso fisico o logico ai servizi governativi di Office 365 United States. Per verificare la cittadinanza, i dipendenti e/o i nuovi candidati a noleggio si incontrano con un delegato di cittadinanza statunitense che è addestrato a esaminare la documentazione per verificare la cittadinanza statunitense. I dipendenti o i nuovi candidati a noleggio devono portare la documentazione richiesta e firmare un modulo di attestazione durante una riunione con il delegato di cittadinanza per la propria area geografica. La riunione deve essere svolta personalmente. Una volta che l'individuo ha incontrato il delegato di cittadinanza e ha fornito la documentazione e le firme necessarie, la cittadinanza delega inoltra una copia dei documenti a Microsoft Staffing Operations che invia la copia per la conservazione dei record.

Il personale con accesso logico al cloud del governo degli Stati Uniti di Office 365, o l'accesso logico o fisico alle offerte del governo degli Stati Uniti di Azure, è tenuto a conformarsi ai requisiti del governo federale delle [informazioni sulla giustizia penale dell'FBI Services](https://www.fbi.gov/services/cjis) (CJIS), inclusa la selezione del personale. Lo screening di CJIS a sostegno del servizio governativo degli Stati Uniti di Office 365 include un controllo dei precedenti penali basato sull'impronta digitale che è aggiudicato dall'arbitro del sistema CJIS designato agli [Stati che si sono iscritti](https://blogs.office.com/2013/10/23/california-and-microsoft-sign-cjis-security-policy-agreement/) alla Microsoft online Programma di supporto per i servizi CJIS.
