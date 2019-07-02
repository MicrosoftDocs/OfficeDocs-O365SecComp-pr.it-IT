---
title: Controlli del personale di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Riepilogo: Panoramica delle procedure di screening del personale Microsoft per Office 365.'
ms.openlocfilehash: 4eb36b8f9f560abea97cc077d16f48a6b9abc6d4
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520706"
---
# <a name="office-365-personnel-controls"></a>Controlli del personale di Office 365 

Lo screening del personale, il processo di revisione e la convalida del comportamento e dello stato del passato per un richiedente, è un importante controllo di attenuazione per impedire il compromesso di servizio di Office 365. Anche se il comportamento passato non è un fattore predittivo perfetto per il comportamento futuro, contribuisce all'identificazione di potenziali attori cattivi. Lo standard di screening del personale Microsoft si applica a tutti i dipendenti Microsoft, gli stagisti e il personale contingente coinvolti nello sviluppo, nel funzionamento o nella distribuzione dei servizi online ai clienti cloud governativi o commerciali. Gli standard di screening per gli ambienti cloud nazionali non gestiti da Microsoft sono definiti dal personale dei partner operativi per ogni ambiente specifico.

## <a name="the-microsoft-personnel-screening-standard"></a>Standard di screening del personale Microsoft

Le procedure di screening del personale per Office 365 sono conformi agli standard aziendali di Microsoft e ai controlli di National Institute of Standards and Technology (NIST) per lo screening del personale. Gli addetti Microsoft che richiedono l'accesso ai seguenti elementi sono soggetti allo standard di screening del personale Microsoft:

- Accesso fisico ai centri dati, colocazioni, sale protette, gabbie, server rack o siti perimetrali che forniscono l'infrastruttura che supporta i servizi online per i clienti governativi o commerciali del cloud.
- Accesso logico ai dati dei clienti cloud governativi o commerciali forniti tramite ambienti gestiti specifici.
- Accesso alla gestione della rete ai dispositivi e ai servizi che trasportano o archiviano i dati dei clienti del cloud governativo o commerciale.

Gli eventi specifici relativi al personale che attivano i requisiti di screening includono:

- Nuovo personale Microsoft inserito nei ruoli in cui la selezione è un requisito definito.
- Personale Microsoft interno trasferito o spostato a un ruolo esistente che attualmente include la schermatura come requisito definito.
- Ruoli esistenti che modificano l'ambito per includere lo screening come requisito definito.

## <a name="screening-enforcement-criteria"></a>Criteri di applicazione della schermatura

Per garantire che solo il personale autorizzato abbia accesso ai dati dei clienti o agli ambienti che richiedono la selezione, si applicano i criteri di applicazione seguenti.

**Solo ambienti cloud degli Stati Uniti**:

- L'accesso ai dati dei clienti o agli ambienti che richiedono la selezione è consentito solo dopo il completamento dell'aggiudicazione e vengono passati i requisiti di screening.
- Il personale Microsoft che non richiede più l'accesso ai dati dei clienti o agli ambienti correlati ha accesso rimosso al momento di lasciare Microsoft o passare a un nuovo ruolo.
- Il personale Microsoft lascia le smart card dell'ambiente schermato con la gestione prima di lasciare gli Stati Uniti.

**Ambienti cloud nazionali**:

- L'operatore di terze parti o il personale trustee dei dati è responsabile della gestione e dell'applicazione dell'accesso per gli ambienti cloud nazionali.

Negli ambienti Microsoft Cloud Services, Access è limitato in base al ruolo di una persona e al tipo di dati coinvolti, come descritto nella tabella seguente. Non è consentito l'accesso ai dati dei clienti all'interno di un cloud degli Stati Uniti in un sito personale qualificato o non qualificato fisicamente all'esterno degli Stati Uniti. L'accesso agli ambienti cloud nazionali è limitato in modo che il personale Microsoft non disponga di accesso tecnico ai dati dei clienti, o sistemi che contengono dati dei clienti, senza l'approvazione da parte dell'operatore di terze parti o del trustee dei dati.

| Ruolo | Accesso ai dati dei clienti | Accesso ai dati di sistema |
|---------------------------------------------------------------------------|------------------------------|---------------------------------|
| Personale qualificato che si trova fisicamente negli Stati Uniti | Consentito | Consentito |
| Personale qualificato che si trova fisicamente all'esterno degli Stati Uniti | Non consentita | Consentito |
| Accesso alle eccezioni internazionali per il personale Microsoft: consente l'accesso logico per il personale Microsoft che non risiede nel paese in cui il governo o i dati del cliente commerciale sono a riposo | Non consentita | Consentito |
| Personale non qualificato (personale non sottoposto a screening che richiede una scorta da personale qualificato) | Consentito con autorizzazione | Consentito con supervisione Escort |

## <a name="microsoft-pre-employment-screening"></a>Screening preimpiego Microsoft

Laddove la legge locale lo consente, il dipartimento di sicurezza globale di Microsoft conduce lo screening di preimpiego. Si tratta di un'analisi di sfondo formale che include i criteri seguenti:

- Verifica del riassunto del richiedente per completezza e accuratezza
- Conferma dei diplomi accademici e professionali
- Indagini su eventuali perdite di credenziali professionali
- Verifica degli ultimi tre datori di lavoro
- Un controllo dei record di polizia per condanne a reato
- Conferma dell'identità da un'identificazione emessa dal governo
- Verifiche del credito se appropriate

Possono essere necessari riesami periodici e/o controlli in background aggiuntivi per alcuni ruoli di gestione, sicurezza o di altro genere, tra cui i dipendenti basati su Stati Uniti nei ruoli che richiedono l'accesso ai dati dei clienti.
Per il personale contingente, il contratto con la terza parte specifica i requisiti di Microsoft per la selezione che devono essere eseguiti da terze parti. Per i controlli in background, la società di terze parti è responsabile di fornire alla verifica Microsoft che è stato eseguito un controllo in background. I risultati del controllo dei precedenti vengono in genere ricevuti tramite posta elettronica dal reparto risorse umane di terze parti. I dipendenti internazionali del personale contrattuale possono essere esonerati dal processo di screening in background a causa di leggi nei paesi che proibiscono i controlli in background.

## <a name="microsoft-employment-screening"></a>Screening di Microsoft Employment

Poiché 2004 negli Stati Uniti, Microsoft richiede dipendenti e stagisti a passare una schermata di registrazione criminale di sette anni nell'ambito dello screening di preimpiego. È incluso lo screening per reati, reati e verifica dell'istruzione e della storia del lavoro.

Prima di assegnare a qualsiasi dipendente Microsoft statunitense o a un subappaltatore assegnato Microsoft statunitense per fornire servizi correlati a Office 365, Microsoft esegue e richiede che i subappaltatori effettuino un controllo dei precedenti costituito da una traccia del numero di previdenza sociale e controllo di fedina penale. I dati di questo controllo di sfondo sono un fattore della decisione di assunzione. Il controllo di fedina penale include un reato di sette anni e un controllo dei precedenti penali nei registri federali, statali e della contea (se applicabile).

Come condizione di impiego e al momento del noleggio, tutti i dipendenti Microsoft sono tenuti a firmare contratti di riservatezza e non divulgazione e a verificare di aver esaminato il manuale dei dipendenti Microsoft.

## <a name="microsoft-cloud-background-check"></a>Controllo del background di Microsoft Cloud

È necessario un controllo dei precedenti cloud di Microsoft per i candidati assunti come dipendenti che forniscono servizi correlati a Office 365 negli Stati Uniti. Gli impiegati Microsoft negli Stati Uniti con accesso ai dati dei clienti devono seguire il processo di controllo dei precedenti del cloud Microsoft richiesto da tutti i servizi di Office 365. Al di fuori degli Stati Uniti, il processo varia. Ad esempio, il cloud Microsoft per la Germania utilizza un modello di approvazione del trustee dei dati, studiato per garantire che il trustee dei dati (società tedesca) e non Microsoft sia in grado di controllare l'accesso ai dati dei clienti. Il cloud Microsoft in Germania viene recapitato dai data center in Germania e i centri operativi (OC) contenenti il personale tecnico del trustee dei dati sono anche in Germania. Sia il datacenter sia le strutture OC sono gestite, gestite e controllate dal trustee dei dati.

Nella tabella seguente sono elencati i controlli eseguiti come parte del controllo dei precedenti del cloud di Microsoft.

| Screening | Descrizione |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ricerca del numero di previdenza sociale | Verifica che il numero di previdenza sociale fornito sia valido. |
| Controllo di precedenti penali | I record penali di sette anni controllano reati di reato e reato allo stato, alla contea e ai livelli locali e, a seconda dei casi, a livello federale. |
| Elenco di controllo delle risorse esterne di Office | Dipartimento del Tesoro elenco di persone e organizzazioni con cui non è consentito ai cittadini degli Stati Uniti e ai residenti permanenti di svolgere attività commerciali. |
| Bureau of Industry and Security List | Elenco del dipartimento di commercio delle persone e degli enti esclusi dall'attività di esportazione. |
| Office of Defense Trade Controls Debarred Persons List (*Aggiunta il 1 ° luglio 2010*) | Dipartimento di stato elenco delle persone e degli enti esclusi dall'impegno nelle attività di esportazione relative al settore della difesa. |

I risultati del controllo dei precedenti cloud di Microsoft sono archiviati nel database dei dipendenti e sono connessi ai sistemi di controllo di accesso di datacenter. Se il controllo dei precedenti cloud di Microsoft scade e il dipendente non lo rinnova, l'accesso ai servizi di Office 365 è revocato e non è più disponibile finché non è stato completato il controllo dei precedenti di Microsoft Cloud. Quando la relazione di lavoro con Microsoft termina, l'accesso a tutti i datacenter è immediatamente revocato.

La cittadinanza degli Stati Uniti è verificata per tutti i dipendenti con accesso fisico o logico ai servizi governativi di Office 365 United States. Per verificare la cittadinanza, i dipendenti e/o i nuovi candidati a noleggio si incontrano con un delegato di cittadinanza statunitense che è addestrato a esaminare la documentazione per verificare la cittadinanza statunitense. I dipendenti o i nuovi candidati a noleggio devono portare la documentazione richiesta e firmare un modulo di attestazione durante una riunione con il delegato di cittadinanza per la propria area geografica. La riunione deve essere svolta personalmente. Una volta che l'individuo ha incontrato il delegato di cittadinanza e ha fornito la documentazione e le firme necessarie, la cittadinanza delega inoltra una copia dei documenti a Microsoft Staffing Operations che invia la copia per la conservazione dei record.

Il personale con accesso logico al cloud del governo degli Stati Uniti di Office 365, o l'accesso logico o fisico alle offerte del governo degli Stati Uniti di Azure, è tenuto a conformarsi ai requisiti del governo federale delle [informazioni sulla giustizia penale dell'FBI Services](https://www.fbi.gov/services/cjis) (CJIS), inclusa la selezione del personale. Lo screening di CJIS a sostegno del servizio governativo degli Stati Uniti di Office 365 include un controllo dei precedenti penali basato sull'impronta digitale, aggiudicato dal giudice dell'agenzia di sistema CJIS negli [Stati che si sono iscritti](https://blogs.office.com/2013/10/23/california-and-microsoft-sign-cjis-security-policy-agreement/) ai servizi Microsoft Online CJIS programma di supporto.
