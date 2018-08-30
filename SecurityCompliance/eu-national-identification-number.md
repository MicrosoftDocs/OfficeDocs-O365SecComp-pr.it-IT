---
title: Numero di identificazione dell'Unione europea nazionale
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: Questo argomento viene illustrato quali un criterio di criterio DLP perdita di dati Cerca qualora venga rilevato un tipo di informazione sensibile numero identificativo nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530741"
---
# <a name="eu-national-identification-number"></a>Numero di identificazione dell'Unione europea nazionale

Questo argomento viene illustrato quali un criterio di criterio DLP perdita di dati Cerca qualora venga rilevato un tipo di informazione sensibile numero identificativo nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Una combinazione di lettere, cifre e caratteri speciali 24
  
### <a name="pattern"></a>Modello

24 caratteri:
  
-  22 lettere (maiuscole o minuscole), cifre, barre rovesciate, barre o segni più 
    
- Due lettere (maiuscole o minuscole), cifre, barre rovesciate, barre, segni più o segni di uguale
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_austria_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_national_id_card` viene trovato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsaustriaeunationalidcard"></a>Keywords_austria_eu_national_id_card

numero di identificazione austriaco
  
numero di identità nazionale
  
numero di identità
  

national id
  
personalausweis italiana österreich
  
## <a name="belgium"></a>Belgio

Per ulteriori informazioni, vedere la sezione "Belgio nazionale Number" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Dieci cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

Dieci cifre senza spazi e i delimitatori
  
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Due cifre che corrispondano all'ordine di nascita
    
- Una cifra che corrisponde al sesso: un numero pari di maschile e una cifra dispari per femmina
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_national_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_bulgaria_national_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_national_number` consente di trovare contenuto corrispondente al formato. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsbulgarianationalnumber"></a>Keywords_bulgaria_national_number

egn
  
egn #
  
Bulgaro numero nazionale
  
numero nazionale
  
social security number

  
nationalnumber #
  
SSN #
  
SSN
  
nationalnumber
  
bnn #
  
bnn
  
numero id personale
  
personalidnumber #
  
ЕДИНЕН ГРАЖДАНСКИ НОМЕР
  
edinen grazhdanski nomer
  
ЕГН
  
ЕГН #
  
## <a name="croatia"></a>Croazia

Per ulteriori informazioni, vedere la sezione "Croazia identità Number" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

Dieci cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 Dieci cifre 
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_cyprus_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_cyprus_eu_national_id_card` viene trovato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordscypruseunationalidcard"></a>Keywords_cyprus_eu_national_id_card

numero di carta d'identità
  
numero identificativo nazionale
  
numero id personale
  
numero di carta d'identità
  
ΤΑΥΤΟΤΗΤΑΣ
  
## <a name="czech-republic"></a>Repubblica Ceca

Per ulteriori informazioni, vedere la sezione "Numero identità nazionale ceco" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Danimarca

Per ulteriori informazioni, vedere la sezione "Danimarca Personal Identification Number" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Una cifra che corrisponde al sesso e century di nascita (maschile numero dispari, numero pari femmina; 1-2: 19 century; 3 e 4: 20 century; 5-6: century ventunesimo)
    
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
    
- Tre cifre che corrispondono a un numero di serie che separa le persone nati nella stessa data
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_estonia_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsestoniaeunationalidcard"></a>Keywords_estonia_eu_national_id_card

codice di identificazione personale
  
numero di identificazione personale
  
numero identificativo nazionale
  
numero nazionale
  
numero id personale
  
personalidnumber #
  
IK
  
isikukood
  
ID kaart
  
## <a name="finland"></a>Finlandia

Per ulteriori informazioni, vedere la sezione "ID nazionale Finlandia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Per ulteriori informazioni, vedere la sezione "Francia nazionale carta d'identità (CNI)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per ulteriori informazioni, vedere la sezione "Numero di carta d'identità Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Per ulteriori informazioni, vedere la sezione "Grecia carta d'identità nazionale" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

11 cifre
  
### <a name="pattern"></a>Modello

11 cifre:
  
-  Una cifra che corrisponde al sesso (maschile 1, 2 femmina, altri numeri sono inoltre disponibili per i cittadini nati prima di 1900 o cittadini con cittadinanza double) 
    
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
    
- Tre cifre che corrispondono a un numero di serie
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordshungaryeunationalidcard"></a>Keywords_hungary_eu_national_id_card

numero di identificazione personale
  
identification number

  
numero id personale
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato
  
### <a name="pattern"></a>Modello

Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato
  
Dal 01 gennaio 2013 per il momento:
  
-  Sette cifre 
    
- Cifra di un controllo
    
- Uno spazio o la lettera maiuscola "W" (distinzione tra maiuscole e minuscole)
    
Prima di 01 gennaio 2013:
  
-  Sette cifre 
    
- Cifra di un controllo
    
- Uno spazio o una lettera maiuscola (maiuscole/minuscole)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione Trova contenuto corrispondente al formato.
    
- È possibile trovare una parola chiave da.
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione Trova contenuto corrispondente al formato.
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsirelandeunationalidcard"></a>Keywords_ireland_eu_national_id_card

numero di servizio della pubblica personali
  
PPS non
  
numero di assicurazione sociale e dei ricavi
  
RSI non
  
numero di identificazione personale
  
identification number

  
numero id personale
  
uimhir phearsanta seirbhíse poiblí
  
uimh. PSP
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Una combinazione di 16 caratteri di lettere e cifre nel formato specificato
  
### <a name="pattern"></a>Modello

Una combinazione di 16 caratteri di lettere e cifre:
  
- Tre lettere che corrispondono ai primi tre consonanti nel nome del gruppo
    
- Tre lettere che corrispondono al primo, terza e quarta consonanti in nome
    
- Due cifre che corrispondono all'ultimo cifre dell'anno di nascita
    
- Una lettera corrispondente per la lettera per il mese di nascita, ovvero lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo lettere da A F, H, L, M, P, R per T (in questo modo, gennaio corrisponde a un e ottobre è R)
    
- Due cifre che corrispondono al giorno del mese di nascita, per poter distinguere tra i due sessi, 40 viene aggiunto al giorno di nascita donne
    
- Quattro cifre che corrisponde all'indicativo di località specifico comune dove nascita della persona (livello nazionale codici vengono utilizzati per i paesi esterni)
    
- Una cifra parità
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_italy_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsitalyeunationalidcard"></a>Keywords_italy_eu_national_id_card

codice personale
  
numero di codice personale
  
numero dei certificati personali
  
codice fiscale
  
personalcodeno #
  
numero id personale
  
codice id personale
  
codice personale
  
Numero certificato personale
  
numero personale
  
numero id personale
  
codice id personale
  
codice fiscale
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

11 cifre e un segno meno nel formato specificato
  
### <a name="pattern"></a>Modello

11 cifre e un segno meno:
  
-  Sei cifre che corrispondono alla data di nascita (DDMMYY) 
    
- Una lineetta
    
- Una cifra che corrisponde al century di nascita ("0" per century diciannovesimo, per century ventesimo "1" e "2" per century ventunesimo)
    
- Quattro cifre, generati in modo casuale
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_latvia_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordslatviaeunationalidcard"></a>Keywords_latvia_eu_national_id_card

codice personale
  
numero di codice personale
  
numero dei certificati personali
  
personalcodeno #
  
numero id personale
  
codice id personale
  
persone kods
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

11 cifre senza spazi e i delimitatori:
  
- Una cifra che corrisponde al sesso della persona e century di nascita
    
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Tre cifre che corrispondono al numero di serie della data di nascita
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_lithuania_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordslithuaniaeunationalidcard"></a>Keywords_lithuania_eu_national_id_card

codice numerico personali
  
numero di identificazione univoco
  
numero del servizio cittadini
  
numero di identificazione univoco
  
uniqueidentityno #
  
codice personale.
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
kodas asmens.
  
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

11 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
- Una cifra che corrisponde al sesso della persona e century di nascita
    
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Tre cifre che corrispondono al numero di serie della data di nascita
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_luxemburg_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_luxemburg_eu_national_id_card` viene trovato. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsluxemburgeunationalidcard"></a>Keywords_luxemburg_eu_national_id_card

id personale
  
numero id personale
  
personalidno #
  
numero id univoco
  
personalidnumber #
  
chiave id univoci
  
codice id personale
  
uniqueidkey #
  
singolo codice
  
id singoli
  
id eindeutige-nummer
  
id eindeutige
  
ID personnelle
  
numéro identificazione personale
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Sette cifre seguite da una lettera
  
### <a name="pattern"></a>Modello

Sette cifre seguite da una lettera:
  
-  Sette cifre 
    
- Una lettera maiuscola (distinzione tra maiuscole e minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_malta_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsmaltaeunationalidcard"></a>Keywords_malta_eu_national_id_card

codice numerico personali
  
numero di identificazione univoco
  
numero del servizio cittadini
  
numero di identificazione univoco
  
uniqueidentityno #
  
kodiċi numerali personali
  
numru ta ' identifikazzjoni uniku
  
numru attività servizz taċ-ċittadin
  
numru ta' identità uniku
  
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

Nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- È possibile trovare una parola chiave da.
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsnetherlandseunationalidcard"></a>Keywords_netherlands_eu_national_id_card

codice numerico personali
  
numero di identificazione univoco
  
numero del servizio cittadini
  
numero di identificazione univoco
  
uniqueidentityno #
  
bsn
  
bsn #
  
codice numerieke persoonlijke
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>Polonia

Per ulteriori informazioni, vedere la sezione "Polonia nazionale ID (PESEL)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portogallo

Per ulteriori informazioni, vedere la sezione "Portogallo cittadini scheda numero" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

13 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

13 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_romania_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_romania_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_romania_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsromaniaeunationalidcard"></a>Keywords_romania_eu_national_id_card

codice numerico personali
  
numero di identificazione univoco
  
cnp
  
cnp #
  
aggiungere
  
PIN #
  
numero di assicurazione
  
insurancenumber #
  
numero di identificazione univoco
  
uniqueidentityno #
  
Cod numerico personale
  
Cod identificare personali
  
identificare unic Cod
  
număr unic personali
  
număr identitate
  
identificare număr personali
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

Dieci cifre che contiene una barra rovesciata
  
### <a name="pattern"></a>Modello

Dieci cifre che contiene una barra rovesciata:
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_slovakia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovakia_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_slovakia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsslovakiaeunationalidcard"></a>Keywords_slovakia_eu_national_id_card

numero di nascita
  
numero identificativo nazionale
  
numero di identificazione personale
  
social security number

  
nationalnumber #
  
SSN #
  
SSN
  
numero nazionale
  
numero id personale
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre nel formato specificato:
  
-  Sette cifre che corrispondono alla data di nascita (DDMMLLL) dove "LLL" corrisponde all'ultima tre cifre dell'anno di nascita 
    
- Due cifre che corrispondono all'area di nascita
    
- Tre cifre che corrispondono a una combinazione di sesso e il numero di serie per le persone nati nello stesso giorno (000-499 per maschile) e 500 e 999 per femmina
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovenia_eu_national_id_card` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordssloveniaeunationalidcard"></a>Keywords_slovenia_eu_national_id_card

codice numerico personali
  
numero di identificazione univoco
  
numero univoco di registrazione
  
numero di identificazione univoco
  
uniqueidentityno #
  
numero univoco cittadini master
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Sette cifre seguite da un carattere
  
### <a name="pattern"></a>Modello

Sette cifre seguite da un carattere
  
- Sette cifre
    
- Una cifra o lettere (maiuscole o minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_spain_eu_national_id_card` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_spain_eu_national_id_card"` viene trovato. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsspaineunationalidcard"></a>Keywords_spain_eu_national_id_card

DNI
  
numero identificativo nazionale
  
numero di identità nazionale
  
numero di assicurazione
  
numero di identificazione personale
  
identità nazionale
  
identità personale non
  
numero di identificazione univoco
  
nationalidno #
  
UniqueID #
  
DNI #
  
nationalid #
  
NIE #
  
NIE
  
nienúmero #
  
número NIE
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
DNI número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>Svezia

Per ulteriori informazioni, vedere la sezione "Svezia-identificativo nazionale" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

