---
title: Numero di identificazione fiscale UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca quando viene rilevato il tipo di informazioni riservate dell'Unione europea imposte Identification Number. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530774"
---
# <a name="eu-tax-identification-number"></a>Numero di identificazione fiscale UE

In questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca quando viene rilevato il tipo di informazioni riservate dell'Unione europea imposte identificazione numero (ID). Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Nove cifre con segno meno facoltativo e barra (/)
  
### <a name="pattern"></a>Modello

Nove cifre con segno meno facoltativo e barra (/):
  
-  Due cifre 
    
- Una lineetta (facoltativa)
    
- Tre cifre
    
- Una barra (facoltativa)
    
- Quattro cifre
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_austria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

Imposta numero
  
numero
  
identificativo fiscale
  
tax id

  
ST.Nr.
  
steuernummer
  
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

11 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Due cifre
    
- "0" o "1"
    
- Una cifra
    
- "0" o "1" o "2" o "3" 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_belgium_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_tax_file_number` viene trovato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

Imposta numero
  
numero di registrazione nazionale
  
identificativo fiscale
  
tax id

  
NIF
  
NIF #
  
registre de numéro nazionale
  
numéro identificazione fiscale
  
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Dieci cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_bulgaria_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_bulgaria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
Uniform numero civile
  
bucn #
  
uniformcivilnumber #
  
Uniform id civile
  
Uniform no civile
  
egn
  
Bulgaro uniform numero civile
  
uniformcivilno #
  
egn #
  
УНИФОРМ ГРАЖДАНСКИ НОМЕР
  
Id униформ
  
Id граждански униформ
  
УНИФОРМ ГРАЖДАНСКИ НЕ
  
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
- Dieci cifre, scelte in modo casuale
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_croatia_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_croatia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

Imposta numero
  
Imposta
  
tax id

  
OID
  
OID #
  
porezni broj
  
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

Otto cifre e una lettera nella serie specificata
  
### <a name="pattern"></a>Modello

Otto cifre e una lettera:
  
-  "0" 
    
- Sette cifre
    
- Una lettera (maiuscole o minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_cyprus_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_cyprus_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_cyprus_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

Imposta numero
  
Imposta
  
tax id

  
codice identificativo fiscale
  
TIC
  
TIC #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ
  
ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Nove o dieci cifre con una barra rovesciata facoltativa
  
### <a name="pattern"></a>Modello

Nove o dieci cifre con un backslashl facoltativi:
  
- Sei cifre 
    
- Una barra rovesciata (facoltativa)
    
- Tre o quattro cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_czech_republic_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_czech_republic_eu_tax_file_number` viene trovato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

Imposta numero
  
Imposta
  
tax id

  
numero personale
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Dieci cifre che contiene un segno meno
  
### <a name="pattern"></a>Modello

Dieci cifre che contiene un hyphenl:
  
-  Sei cifre che corrispondono alla data di nascita (DDMMYY) 
    
- Una lineetta
    
- Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde a century di nascita e l'ultima cifra corrisponde in genere dell'individuo (dispari per maschile e anche per femmina)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_denmark_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_denmark_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

Imposta numero
  
Imposta
  
tax id

  
numero CPR
  
CPR #
  
skat nummer
  
id skat
  
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre:
  
-  Una cifra che corrisponde al sesso e century di nascita in un numero dispari indica maschile e il numero pari femmina nel modo seguente: 1, 2 per century diciannovesimo; 3, 4 per century ventesimo; e 5, 6 per century ventunesimo 
    
- Sei cifre che corrispondono alla data di nascita (AAMMGG)
    
- Tre cifre che corrispondono a un numero di serie che separa le persone nati nella stessa data
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_estonia_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_estonia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

Imposta numero
  
Imposta
  
tax id

  
codice personale
  
maksunumber
  
id maksu
  
isikukood
  
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

Una combinazione di caratteri 11 cifre, lettere, e plus e segno meno
  
### <a name="pattern"></a>Modello

Una combinazione di caratteri 11 cifre, lettere, e plus e segno meno:
  
- Sei cifre
    
- Uno dei seguenti: un segno di addizione, un segno di sottrazione o la lettera "A" (non maiuscole/minuscole) dove si intende il segno di addizione nati tra 1800 1899 meno accedere mezzi nati tra 1900-1999 e "A" indica nati 2000 e dopo
    
- Tre cifre
    
- Una lettera o un numero
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_finland_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_finland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

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
  
## <a name="france"></a>Francia

### <a name="format"></a>Formato

13 cifre per singoli utenti e i numeri di nove per le entità
  
### <a name="pattern"></a>Modello

13 cifre per singoli utenti:
  
- Una cifra che deve essere 0, 1, 2 o 3
    
- 12 cifre
    
Nove cifre per le entità
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_france_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_france_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_france_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

numero di identificazione fiscale
  
Imposta numero
  
tax id

  
numéro identificazione fiscale
  
## <a name="germany"></a>Germania

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
  
- La funzione `Func_germany_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_germany_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_germany_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
tax id

  
taxid #
  
numero di identificazione fiscale
  
Identificazione delle imposte non.
  
steuernummer
  
id steuer
  
steueridentifikationsnummer
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_greece_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_greece_eu_tax_file_number` viene trovato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

afm
  
tin

  
id imposta non.
  
id imposta non
  
numero di identificazione fiscale
  
numero del Registro di sistema fiscale
  
imposte non del Registro di sistema.
  
afm #
  
ID #
  
taxidno #
  
taxregistryno #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
aφμ
  
aφμ αριθμός
  
ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ.
  
ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Dieci cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Dieci cifre:
  
-  Una cifra che deve essere "8" 
    
- Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dei singoli
    
- Tre cifre che corrispondono al numero generato casualmente per distinguere i singoli utenti nati nello stesso giorno
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_hungary_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

numero di identificazione fiscale ungherese
  
ID ungherese
  
codice fiscale
  
numero IVA
  
Imposta autorità non
  
codice fiscale identità fiscale
  
taxidnumber #
  
ID #
  
hungatiantin #
  
Identificazione delle imposte non
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Sette cifre seguite da una lettera senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Sette cifre seguite da una lettera:
  
-  Sette cifre 
    
- Una lettera (maiuscole o minuscole)
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_ireland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_ireland_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_ireland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

servizio della pubblica alcun
  
servizio della pubblica personale non
  
PPS non
  
personale service n
  
PPS service n
  
ppsno #
  
irlandese pps non
  
publicserviceno #
  
numero di servizio della pubblica personali
  
uimhir phearsanta seirbhíse poiblí
  
uimh PPS
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

16 lettere e cifre nel formato specificato
  
### <a name="pattern"></a>Modello

16 lettere e cifre:
  
-  Tre lettere che corrispondono ai primi tre consonanti nel nome del gruppo 
    
- Tre lettere che corrispondono al primo, terza e quarta consonanti in nome
    
- Due cifre che corrispondono all'ultimo cifre dell'anno di nascita
    
- Una cifra che corrisponde al mese di nascita, ovvero lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo lettere da A F, H, L, M, P, R per T (in questo modo, gennaio corrisponde a un e ottobre è R)
    
- Due cifre che corrispondono al giorno del mese di nascita dove 40 viene aggiunto al giorno di nascita per capi distinguere dai maschi
    
- Quattro cifre che corrispondono all'indicativo di località specifico comune dove nascita della persona, a livello nazionale codici vengono utilizzati per i paesi esterni
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_italy_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_italy_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
tax id

  
taxid #
  
codice fiscale
  
codice fiscale
  
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre nel formato specificato
  
-  Sei cifre che corrispondono alla data di nascita (DDMMYY) 
    
- Una cifra che corrisponde al century di nascita dove "0" corrisponde al diciannovesimo century "1" corrisponde al ventesimo century e "2" corrisponde al ventunesimo century
    
- Quattro cifre
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_latvia_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_latvia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
tax id

  
taxid #
  
numero di identificazione fiscale
  
Identificazione delle imposte non.
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

11 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

11 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_lithuania_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_lithuania_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

Imposta numero
  
imposte no.
  
Imposta no #
  
Numero imposta #
  
Numero imposta
  
tax id

  
taxid #
  
numero di identificazione fiscale
  
Identificazione delle imposte non.
  
id mokesčių
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre:
  
-  11 cifre 
    
- Due cifre di controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_luxemburg_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_luxemburg_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_luxemburg_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
tax id

  
taxid #
  
numero di identificazione fiscale
  
Identificazione delle imposte non.
  
steuernummer
  
id steuer
  
steueridentifikationsnummer
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Per i cittadini Maltese: 7 cifre e una lettera nella serie specificata
  
Maltese non cittadini ed entità Maltese: 9 cifre
  
### <a name="pattern"></a>Modello

Sterlina maltese cittadini: 7 cifre e una lettera
  
-  Sette cifre 
    
- Una lettera (maiuscole o minuscole)
    
Maltese non cittadini ed entità Maltese: 9 cifre
  
-  9 cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_malta_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_malta_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:
  
- La funzione `Func_malta_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
tax id

  
taxid #
  
numero di identificazione fiscale
  
Identificazione delle imposte non.
  
numru tat-taxxa
  
ID tat-taxxa
  
numru ta ' identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

Nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

9 cifre 
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_netherlands_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_netherlands_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

numero di identificazione fiscale Paesi Bassi
  
identificazione imposte Paesi Bassi
  
numero di identificazione fiscale Olanda
  
identificazione imposte Olanda
  
numero di identificazione fiscale
  
id imposta olandese
  
numero di identificazione olandese
  
tax id

  
Imposta id #
  
Imposta numero
  
Imposta no #
  
Imposta #
  
tin

  
ID #
  
ID Paesi Bassi
  
ID Olanda
  
Paesi Bassi belasting identificatienummer
  
identificatienummer van belasting
  
belasting identificatienummer
  
Paesi Bassi belasting identificatie
  
Paesi Bassi belasting id nummer
  
Paesi Bassi belastingnummer
  
BTW nummer
  
Nederlandse belasting identificatie
  
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

Undici cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Undici cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_poland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_poland_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_poland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
nip
  
da nip #
  
tax id

  
Imposta id #
  
id da nip
  
da nip id #
  
numero di identificazione fiscale
  
Identificazione delle imposte non.
  
numero IVA
  
IVA no.
  
vatno #
  
id IVA
  
id IVA #
  
numero identyfikacji podatkowej
  
polski numero identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>Portogallo

### <a name="format"></a>Formato

Nove cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_portugal_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_portugal_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_portugal_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

Imposta numero
  
imposte no.
  
taxno #
  
Numero imposta #
  
Numero imposta
  
NIF
  
NIF #
  
numero fiscale
  
número de identificação fiscale
  
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

13 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

13 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_romania_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_romania_eu_tax_file_number` viene trovato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
codice fiscale
  
Imposta i file non
  


tax file number
  
Imposta n
  
Imposta numero
  
taxid #
  
taxno #
  
ID ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

10 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovakia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovakia_eu_tax_file_number` viene trovato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
codice fiscale
  
id stagno
  
no stagno
  
id stagno slovacco
  
tin

  
Imposta i file non
  


tax file number
  
Imposta n
  
Imposta numero
  
taxid #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

Otto cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovenia_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_slovenia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
codice fiscale
  
id stagno
  
no stagno
  
id stagno sloveno
  
tin

  
Imposta i file non
  


tax file number
  
Imposta n
  
Imposta numero
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
Številka davčne datoteke
  
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Otto o sette cifre e uno o due lettere nella serie specificata
  
### <a name="pattern"></a>Modello

Spagnolo persone con una carta d'identità nazionale Spagna:
  
-  Otto cifre 
    
- Una lettera maiuscola (maiuscole/minuscole) 
    
Non residenti Spaniards senza un carta d'identità nazionale Spagna
  
- Una lettera maiuscola "L" (maiuscole/minuscole)
    
- Sette cifre
    
- Una lettera maiuscola (maiuscole/minuscole) 
    
Spaniards residenti minori di 14 anni senza un Spagna nazionale carta d'identità:
  
- Una lettera maiuscola "K" (maiuscole/minuscole)
    
-  Sette cifre 
    
- Una lettera maiuscola (maiuscole/minuscole)
    
Stranieri con numero di identificazione del Foreigner
  
- Vale a dire maiuscoli una lettera "X", "Y" o "Z" (maiuscole/minuscole) 
    
- Sette cifre
    
- Una lettera maiuscola (maiuscole/minuscole) 
    
Stranieri senza numero di identificazione del Foreigner
  
- Una lettera maiuscola che è "M" (maiuscole/minuscole) 
    
- Sette cifre
    
- Una lettera maiuscola (maiuscole/minuscole) 
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_spain_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_spain_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_spain_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
codice fiscale
  
id cif
  
cif non
  
id lingua spagnola cif
  
cif
  
Imposta i file non
  
numero cif spagnolo
  


tax file number
  
Spagnolo cif non
  
Imposta n
  
Imposta numero
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto corporativo
  
número de identificación fiscali
  
cif número
  
cifnúmero #
  
## <a name="sweden"></a>Svezia

### <a name="format"></a>Formato

Dieci cifre e un simbolo nella serie specificata
  
### <a name="pattern"></a>Modello

Dieci cifre e un simbolo:
  
-  Sei cifre che corrispondono alla data di nascita (AAMMGG) 
    
- Un segno di addizione, segno di sottrazione o barra rovesciata
    
- Tre cifre che rendono l'identificazione dei numeri univoco where: 
    
  - Per i numeri rilasciati prima 1990, la cifra settima e ottava identificare la provincia di nascita o utenti foreign-born
    
  - La cifra nella posizione nona indica sesso per entrambi dispari per maschile o persino femmina
    
- Cifra di un controllo
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_sweden_eu_tax_file_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_sweden_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
id imposta non.
  
codice fiscale
  
tax identification

  
Imposta identificazione #
  
imposte no.
  
Imposta #
  
taxid #
  
file fiscali
  
imposte non file.
  
numero id personale
  
skatt id nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>REGNO UNITO

### <a name="format"></a>Formato

Riferimento fiscale univoco (UTR): 10 cifre senza spazi e i delimitatori
  
Numero di assicurazione nazionale (NINO): Per ulteriori informazioni, vedere la sezione "Regno Unito di numero di assicurazione nazionale (NINO)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Modello

Riferimento fiscale univoco (UTR): 10 cifre
  
Numero di assicurazione nazionale (NINO): Per ulteriori informazioni, vedere la sezione "Regno Unito di numero di assicurazione nazionale (NINO)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_uk_eu_tax_file_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_uk_eu_tax_file_number` viene trovato. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
id imposta non.
  
codice fiscale
  
tax identification

  
Imposta identificazione #
  
imposte no.
  
Imposta #
  
taxid #
  
file fiscali
  
imposte non file.
  
## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

