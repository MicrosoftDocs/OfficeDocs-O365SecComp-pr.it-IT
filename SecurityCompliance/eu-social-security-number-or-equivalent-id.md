---
title: Codice di preVidenza sociale dell'Unione europea o ID equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando rileva il numero di preVidenza sociale dell'Unione europea o il tipo di informazioni riservate ID equivalente. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: abcefb6930e9c02d2f32d84b65accfecf1e20d95
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216526"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>Codice di preVidenza sociale dell'Unione europea o ID equivalente

In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP, Data Loss Prevention), quando viene rilevato il codice fiscale dell'Unione europea (SSN) o il tipo di informazioni sensibili ID equivalente. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

10 cifre nel formato specificato
  
### <a name="pattern"></a>Modello

10 cifre:
  
-  Tre cifre che corrispondono a un numero di serie 
    
- Una cifra di controllo
    
- Sei cifre che corrispondono alla data di nascita (GGMMAA)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_austria_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

previdenza sociale No
  
social security number

  

social security code
  
numero assicurativo
  
SSN austriaco
  
SSN
  
SSN
  
codice assicurativo
  
codice assicurativo #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale Sicherheit kein
  
Versicherungsnummer
  
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_belgium_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

numero nazionale belga
  
numero nazionale
  
social security number

  
nationalnumber #
  
SSN
  
SSN
  
nationalnumber
  
BNN
  
BNN
  
numero ID personale
  
personalidnumber #
  
numéro nazionale
  
numéro de sécurité

  
numéro d'assuré
  
identificazione nazionale
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

11 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

 11 cifre: 
  
-  Dieci cifre 
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_croatia_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

numero di identificazione personale
  
numero di cittadino Master
  
numero di identificazione nazionale
  
social security number

  
nationalnumber #
  
SSN
  
SSN
  
nationalnumber
  
BNN
  
BNN
  
numero ID personale
  
personalidnumber #
  
OIB
  
Osobni identifikacijski broj
  
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Dieci cifre e una barra rovesciata nel modello specificato
  
### <a name="pattern"></a>Modello

Dieci cifre e una barra rovesciata:
  
- Sei cifre che corrispondono alla data di nascita (AAMMGG): 
    
- Una barra rovesciata
    
- Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_czech_republic_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

numero di nascita
  
numero di identificazione nazionale
  
numero di identificazione personale
  
social security number

  
nationalnumber #
  
SSN
  
SSN
  
numero nazionale
  
numero ID personale
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Dieci cifre e un trattino nel modello specificato
  
### <a name="pattern"></a>Modello

Dieci cifre e un trattino:
  
- Sei cifre che corrispondono alla data di nascita (GGMMAA) 
    
- Una lineetta
    
- Quattro cifre che corrispondono a un numero di sequenza
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_denmark_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

numero di identificazione personale
  
numero di identificazione nazionale
  
social security number

  
nationalnumber #
  
SSN
  
SSN
  
numero nazionale
  
numero ID personale
  
personalidnumber #
  
CPR-Nummer
  
personnummer
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinazione di 11 caratteri nel formato specificato
  
### <a name="pattern"></a>Modello

Una combinazione di 11 caratteri nel formato specificato:
  
-  Sei cifre 
    
- Un'istanza di una delle opzioni seguenti:
    
  - Segno più
    
  - Segno meno
    
  - La lettera "A" (senza distinzione tra maiuscole e minuscole)
    
- Tre cifre
    
- Una lettera o una cifra
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_finland_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

identification number

  
ID personale
  
numero di identità
  
numero di identificazione nazionale finlandese
  
personalidnumber #
  
numero di identificazione nazionale
  
numero ID
  
ID nazionale No.
  
numero ID nazionale
  
ID No
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
numero identiteetti
  
Suomen Kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
Kansallinen tunnus numero
  
hetu
  
## <a name="france"></a>Francia

Per informazioni dettagliate, vedere la sezione "Francia social preVidenza (INSEE)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Nove cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_hungary_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

codice di previdenza sociale ungherese
  
social security number

  
SocialSecurityNumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
Taj
  
Taj
  
SSN
  
SSN
  
previdenza sociale No
  
ÁFA
  
közösségi adószám
  
Általános forgalmi Adó szám
  
hozzáadottérték Adó
  
ÁFA szám
  
Magyar ÁFA szám
  
## <a name="portugal"></a>Portogallo

Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).
  
## <a name="spain"></a>Spagna

Per informazioni dettagliate, vedere la sezione "Spagna Social preVidenza sociale (SSN)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="sweden"></a>Svezia

### <a name="format"></a>Formato

12 cifre senza spazi e delimitatori
  
### <a name="pattern"></a>Modello

12 cifre:
  
-  Otto cifre che corrispondono alla data di nascita (AAAAMMGG) 
    
- Tre cifre che corrispondono a un numero di serie in cui: 
    
  - L'ultima cifra del numero di serie indica il sesso per l'assegnazione di un numero dispari per il maschio e per un numero pari per la femmina
    
  - Fino a 1990, l'assegnazione del numero di serie corrispondeva alla contea in cui è Nato il portatore del numero o (se è nato prima del 1947) dove viveva, secondo i registri delle tasse, il 1 ° gennaio 1947, con un codice speciale (solitamente 9 come settima cifra) per immigrati 
    
- Una cifra di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
- Viene trovata una `Keywords_sweden_eu_ssn_or_equivalent` parola chiave from. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

numero ID personale
  
identification number

  
ID personale No
  
identità No
  
identificazione no
  
identificazione personale No
  
ID personnummer
  
ID personligt-Nummer
  
ID unikt-Nummer
  
personnummer
  
identifikationsnumret
  
personnummer
  
identifikationsnumret #
  
## <a name="see-also"></a>Vedere anche

[Cosa individuano le tipologie di informazioni sensibili](what-the-sensitive-information-types-look-for.md)

