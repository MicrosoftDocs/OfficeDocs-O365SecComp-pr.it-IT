---
title: Numero di passaporto UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile il numero di passaporto UE. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530884"
---
# <a name="eu-passport-number"></a>Numero di passaporto UE

Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile il numero di passaporto UE. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Una lettera seguita da sette cifre e da uno spazio facoltativo
  
### <a name="pattern"></a>Modello

Una combinazione di una lettera, sette cifre e uno spazio:
  
- Una lettera (senza distinzione tra maiuscole/minuscole)
    
- Uno spazio (facoltativo)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_austria_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto austriaco  <br/> Passport non  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

Due lettere seguite da sei cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere e seguita da sei cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_belgium_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto belga  <br/> Passport non  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_bulgaria_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_bulgaria_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto bulgaro  <br/> Passport non  <br/> НОМЕР НА ПАСПОРТА  <br/> |
   
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_croatia_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_croatia_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto croato  <br/> Passport non  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

Una lettera seguita da 6 a 8 cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una lettera seguita da sei a otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_cyprus_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_cyprus_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto Cipro  <br/> Passport non  <br/> ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ  <br/> |
   
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Otto cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre senza spazi o delimitatori
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_czech_republic_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_czech_republic_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto ceca  <br/> Passport non  <br/> pas cestovní  <br/> PAS  <br/> |
   
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_denmark_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_denmark_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto danese  <br/> Passport non  <br/> PAS  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Una lettera seguita da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una lettera seguita da sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_estonia_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_estonia_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto estone  <br/> Passport non  <br/> eesti kodaniku pass  <br/> |
   
## <a name="finland"></a>Finlandia

Per ulteriori informazioni, vedere la sezione "Numero di passaporto Finlandia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>Francia

Per ulteriori informazioni, vedere la sezione "Numero di passaporto Francia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per ulteriori informazioni, vedere la sezione "Numero di passaporto Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Due lettere seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da 7 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_greece_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_greece_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto greca  <br/> Passport non  <br/> ΔΙΑΒΑΤΗΡΙΟ  <br/> |
   
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Due lettere seguite da sei o sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da sei o sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_hungary_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto ungherese  <br/> Passport non  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguiti da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_ireland_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_ireland_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto irlandese  <br/> Passport non  <br/> PAS  <br/> passport  <br/> passeport  <br/> numero passeport  <br/> |
   
## <a name="italy"></a>Italia

### <a name="format"></a>Formato

Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguiti da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_italy_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_italy_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|numero di passaporto italiano  <br/> Repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> numero di passaporto  <br/> numero di passaporto italiana  <br/> numero di passaporto  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere o cifre seguiti da sette cifre:
  
- Due cifre o lettere (senza distinzione tra maiuscole/minuscole)
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_latvia_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_latvia_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto lettone  <br/> Passport non  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Otto cifre o lettere senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre o lettere (non maiuscole/minuscole)
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_lithuania_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_lithuania_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto lithunian  <br/> Passport non  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

Otto cifre o lettere senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre o lettere (non maiuscole/minuscole)
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_nation_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_nation_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto lettone  <br/> Passport non  <br/> passnummer  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

 Sette cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_malta_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto maltese  <br/> Passport non  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

Nove lettere o cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Nove lettere o cifre
  
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_netherlands_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_netherlands_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|numero di passaporto olandese  <br/> numero di passaporto  <br/> numero di passaporto Paesi Bassi  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>Polonia

Per ulteriori informazioni, vedere la sezione "Numero di passaporto Polonia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portogallo

### <a name="format"></a>Formato

Una lettera seguita da sei cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una lettera seguita da sei cifre:
  
- Una lettera (senza distinzione tra maiuscole/minuscole)
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_portugal_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_portugal_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto portoghese  <br/> Passport non  <br/> número passaporte  <br/> |
   
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

Otto o nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

Otto o nove cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_romania_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_romania_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto rumeno  <br/> Passport non  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

Una cifra o una lettera seguito da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una cifra o una lettera (non maiuscole/minuscole) seguito da sette cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovakia_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovakia_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto slovacco  <br/> Passport non  <br/> Číslo pasu  <br/> |
   
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

Due lettere seguite da sette cifre senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Due lettere seguite da sette cifre:
  
- La lettera "P"
    
- Una lettera maiuscola
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovenia_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovenia_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|numero di passaporto  <br/> numero di passaporto sloveno  <br/> Passport non  <br/> Številka potnega lista  <br/> |
   
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Una combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori
  
### <a name="pattern"></a>Modello

Una combinazione di otto o nove caratteri di numeri e lettere:
  
-  Due cifre o lettere selezionate 
    
- Una cifra o una lettera (facoltativo)
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_spain_eu_passport_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_spain_eu_passport_number` viene trovato. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|passport  <br/> passport Spagna  <br/> Rubrica di passaporto  <br/> numero di passaporto  <br/> Passport non  <br/> libreta pasaporte  <br/> número pasaporte  <br/> España pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>Svezia

Per ulteriori informazioni, vedere la sezione "Numero di passaporto Svezia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="uk"></a>REGNO UNITO

Per ulteriori informazioni, vedere la sezione "US / numero di passaporto Regno Unito" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

