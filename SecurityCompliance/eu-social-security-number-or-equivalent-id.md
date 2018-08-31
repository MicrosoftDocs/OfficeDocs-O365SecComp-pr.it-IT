---
title: ID di numero di previdenza sociale UE o equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile numero di previdenza sociale UE o l'ID equivalenti. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530681"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>ID di numero di previdenza sociale UE o equivalente

Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile UE numero di previdenza sociale (SSN) o l'ID equivalenti. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

10 cifre nel formato specificato
  
### <a name="pattern"></a>Modello

10 cifre:
  
-  Tre cifre che corrispondono a un numero di serie 
    
- Cifra di un controllo
    
- Sei cifre che corrispondono alla data di nascita (DDMMYY)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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

sicurezza sociale non
  
social security number

  

social security code
  
numero di assicurazione
  
ssn austriaco
  
SSN #
  
SSN
  
codice di assicurazione
  
codice di assicurazione #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_belgium_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_belgium_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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
  
SSN #
  
SSN
  
nationalnumber
  
bnn #
  
bnn
  
numero id personale
  
personalidnumber #
  
numéro nazionale
  
numéro de sécurité

  
g numéro'assuré
  
identifiant nazionale
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

11 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 11 cifre: 
  
-  Dieci cifre 
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_croatia_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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
  
numero di cittadini master
  
numero identificativo nazionale
  
social security number

  
nationalnumber #
  
SSN #
  
SSN
  
nationalnumber
  
bnn #
  
bnn
  
numero id personale
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Dieci cifre e una barra rovesciata nella serie specificata
  
### <a name="pattern"></a>Modello

Dieci cifre e una barra rovesciata:
  
- Sei cifre che corrispondono alla data di nascita (AAMMGG): 
    
- Una barra rovesciata
    
- Tre cifre che corrispondono a un numero di serie che separa le persone nati nella stessa data
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_czech_republic_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_czech_republic_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_czech_republic_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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
  
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Dieci cifre e un segno meno nella serie specificata
  
### <a name="pattern"></a>Modello

Dieci cifre e un segno meno:
  
- Sei cifre che corrispondono alla data di nascita (DDMMYY) 
    
- Una lineetta
    
- Quattro cifre che corrispondono a un numero di sequenza
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_denmark_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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
  
numero identificativo nazionale
  
social security number

  
nationalnumber #
  
SSN #
  
SSN
  
numero nazionale
  
numero id personale
  
personalidnumber #
  
CPR nummer
  
personnummer
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinazione di 11 cifre nel formato specificato
  
### <a name="pattern"></a>Modello

Una combinazione di 11 cifre nel formato specificato:
  
-  Sei cifre 
    
- Un'istanza di uno dei seguenti:
    
  - Simbolo Plus
    
  - Meno simbolo
    
  - La lettera "A" (maiuscole o minuscole)
    
- Tre cifre
    
- Una lettera o una cifra
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_finland_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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

  
id personale
  
numero di identità
  
numero id nazionale Finlandia
  
personalidnumber #
  
numero identificativo nazionale
  
numero ID
  
id nazionale non.
  
numero identificativo nazionale
  
ID non
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
numero identiteetti
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
numero di tunnus kansallinen
  
hetu
  
## <a name="france"></a>Francia

Per ulteriori informazioni, vedere la sezione "Francia numero di previdenza sociale (INSEE)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per ulteriori informazioni, vedere la sezione "Numero di carta d'identità Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

Per ulteriori informazioni, vedere la sezione "Grecia carta d'identità nazionale" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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

numero di previdenza sociale ungherese
  
social security number

  
SocialSecurityNumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
taj
  
taj #
  
SSN
  
SSN #
  
sicurezza sociale non
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
áfa magyar szám
  
## <a name="portugal"></a>Portogallo

Per ulteriori informazioni, vedere la sezione "Portogallo cittadini scheda numero" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="spain"></a>Spagna

Per ulteriori informazioni, vedere la sezione "Spagna numero di previdenza sociale (SSN)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="sweden"></a>Svezia

### <a name="format"></a>Formato

12 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

12 cifre:
  
-  Otto cifre che corrispondono alla data di nascita (AAAAMMGGG) 
    
- Tre cifre che corrispondono a un numero di serie dove: 
    
  - L'ultima cifra del numero di serie indica sesso per l'assegnazione di un numero dispari di maschile e un numero pari di femmina
    
  - Fino a 1990, l'assegnazione del numero di serie corrispondeva alla provincia in cui portanti del numero di nascita o (se nati prima 1947) cui ha effettuato con stato vive, in base ai record di imposta su 1 gennaio 1947, con un codice speciale (in genere 9 come 7 cifre) per immigranti 
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_sweden_eu_ssn_or_equivalent` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato. 
    
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

numero id personale
  
identification number

  
id personale non
  
identità non
  
identificazione non
  
identificazione personale non
  
id personnummer
  
id personligt-nummer
  
id unikt-nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

