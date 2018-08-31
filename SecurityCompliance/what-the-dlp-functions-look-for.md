---
title: Cosa individuano le funzioni DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: I tipi di informazioni riservate cercare un modello specifico e il grado di confermare accertandosi corretto formattazione applicate checksum e cercando pertinenti parole chiave o altre informazioni. Alcune di queste funzionalità viene eseguita da funzioni interne. In questo argomento viene illustrato che queste funzioni aspetto, che consentono di comprendere il funzionano i tipi di informazioni riservate predefiniti.
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013760"
---
# <a name="what-the-dlp-functions-look-for"></a>Cosa individuano le funzioni DLP

Prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, come il numero di carta di credito e il numero di carta di debito EU, pronti per essere utilizzati nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.
  
In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti. Per ulteriori informazioni, vedere [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).
  
## <a name="funcusdate"></a>Func_us_date

Questa funzione Cerca una data in formato comunemente utilizzata negli Stati Uniti Sono inclusi i formati "giorno/mese/anno", "mese-giorno-anno" e "mese il giorno anno". I nomi o abbreviazioni mesi non sono distinzione tra maiuscole e minuscole. 
  
Esempi:
  
- 2 dicembre 2016
    
- 2 DEC 2016
    
- DEC 2016 02
    
- 2/12/2016
    
- 12/02/16
    
- DEC-2-2016
    
- 12-2-16
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gennaio febbraio Mar. Apr. maggio giugno luglio agosto settembre ottobre Dec novembre.
    
## <a name="funceudate"></a>Func_eu_date

Questa funzione consente di cercare una data nel formato comunemente usato nell'UE e nella maggior parte delle aree geografiche al di fuori degli Stati Uniti. Sono inclusi i formati "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.
  
Esempi:
  
- 2 Dec 2016
    
- dec 02 2016
    
- 2 Dec 16
    
- 2/12/2016
    
- 12/02/16
    
- 2-dic-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Gennaio febbraio Mar. Apr. maggio giugno luglio agosto settembre ottobre Dec novembre.
    
- Olandese
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan CTP di febbraio maart apr mei giugno luglio agosto set settembre ottobre okt novembre dicembre
    
- Francese
    
  - janvier, février, mars, avril, mai, juillet ADR, août, septembre, octobre, novembre, décembre
    
  - janv. févr. Mar avril mai ADR juil. août settembre. ott novembre. déc.
    
- Tedesco
    
  - jänuar, februar, märz, aprile, mai, juni juli, agosto, settembre, oktober, novembre, dezember
    
  - Gen. / Jän. Febbraio März Apr. Mai Juni Juli agosto settembre Okt. Dez novembre.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - Genn. febbr. Mar. APR. magg. giugno luglio ag. sett. ott. novembre. dic.
    
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar router di confine area mai giugno, luglio fa stabiliti novembre dez
    
- Spagnolo
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero CTP di febbraio. marzo abr. mayo Giu luglio. insieme/agosto settembre. ott novembre. dic.
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (obsoleto)

> [!NOTE]
> Questa funzione è deprecata perché supporta solo portoghese i nomi dei mesi, che ora sono inclusi nel `Func_eu_date` funzione sopra. 
  
Questa funzione Cerca una data in formato comunemente utilizzata nelle portoghese. Il formato per questa funzione è uguale `Func_eu_date`, diverse solo nella lingua utilizzata.
  
Esempi:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 12/02/16
    
- 2-Dez-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Portoghese
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar router di confine area mai giugno, luglio fa stabiliti novembre dez
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (obsoleto)

> [!NOTE]
> Questa funzione è deprecata perché supporta solo olandese i nomi dei mesi, che ora sono inclusi nel `Func_eu_date` funzione sopra. 
  
Questa funzione Cerca una data in formato comunemente utilizzata in olandese. Il formato per questa funzione è uguale `Func_eu_date`, diverse solo nella lingua utilizzata.
  
Esempi:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 12/02/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomi dei mesi accettati:
  
- Olandese
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan CTP di febbraio maart apr mei giugno luglio agosto set settembre ottobre okt novembre dicembre
    
## <a name="funcexpirationdate"></a>Func_expiration_date

Questa funzione Cerca una data in formati comunemente utilizzata dalle schede di dare e in cui escludere giorni favore dei mesi. Questa funzione corrispondenti date in formato "mese/anno", "mese-anno", "[nome del mese] anno" e "anno [abbreviazione mese]". I nomi o abbreviazioni mesi non sono distinzione tra maiuscole e minuscole.
  
Esempi
  
- MM/AA -- ad esempio, 01/11 o 1/11
    
- MM/AAAA -- ad esempio, 01/2011 o 1/2011
    
- MM-AA -- ad esempio, 01-22 o 1-11
    
- MM-AAAA-- ad esempio, 01-2000 o 1-2000
    
I formati seguenti supportano AA o AAAA:
  
- Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10
    
- Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"
    
- MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"
    
- Mese/YYYY, ad esempio, "gennaio/2010" o "Gen/2010" o ' gennaio/10' o ' Jan/10'
    
Nomi dei mesi accettati:
  
- Inglese
    
  - Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - CTP di febbraio gen Mar Apr maggio giugno luglio agosto settembre Oct Dec novembre
    
## <a name="funcusaddress"></a>Func_us_address

Questa funzione cerca il nome di uno stato membro degli Stati Uniti o un'abbreviazione postale seguita da un CAP valido, esattamente come per gli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.
  
Esempi:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

