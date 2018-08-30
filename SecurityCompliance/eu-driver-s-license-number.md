---
title: Numero della patente di Guida di Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile numero della patente di Guida dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530763"
---
# <a name="eu-drivers-license-number"></a>Numero della patente di Guida di Unione europea

Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile numero della patente di Guida dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Otto cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_austria_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_driver's_license_number` viene trovato. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> titolo della patente di Guida  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/>  che influisce sul numero di licenza  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein italiana osterreich  <br/> |
   
## <a name="belgium"></a>Belgio

### <a name="format"></a>Formato

10 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_belgium_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein nr  <br/> fuehrerschein Nr  <br/> fuehrerschein nr  <br/> |
   
## <a name="bulgaria"></a>Bulgaria

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_bulgaria_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_bulgaria_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС  <br/> СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО  <br/> СУМПС  <br/> ШОФЬОРСКА КНИЖКА  <br/> |
   
## <a name="croatia"></a>Croazia

### <a name="format"></a>Formato

Otto cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_croatia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_croatia_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>Cipro

### <a name="format"></a>Formato

12 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

12 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_cyprus_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_cyprus_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> |
   
## <a name="czech-republic"></a>Repubblica Ceca

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Otto lettere e cifre:
  
- Due lettere (maiuscole o minuscole)
    
- Uno spazio (facoltativo)
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_czech_republic_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_czech_republic_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> Řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>Danimarca

### <a name="format"></a>Formato

Otto cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

Otto cifre
  
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_denmark_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_denmark_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>Estonia

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Due lettere e sei cifre:
  
-  Le lettere "ET" (maiuscole o minuscole) 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_estonia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_estonia_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> 
permis de conduire  <br/> |
   
## <a name="finland"></a>Finlandia

### <a name="format"></a>Formato

10 cifre contenenti una lineetta
  
### <a name="pattern"></a>Modello

10 cifre che contiene un segno meno:
  
-  Sei cifre 
    
- Una lineetta
    
-  Quattro cifre 
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_finland_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_finland_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>Francia

Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida di Francia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Germania

Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida tedesca" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grecia

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 9 cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_greece_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_greece_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|dlL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> ΔΕΙΑ ΟΔΉΓΗΣΗΣ  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>Ungheria

### <a name="format"></a>Formato

Due lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Due lettere e sei cifre:
  
-  Due lettere (maiuscole o minuscole) 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_hungary_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formato

Sei cifre seguite da quattro lettere
  
### <a name="pattern"></a>Modello

Sei cifre e quattro lettere:
  
- Sei cifre
    
- Quattro lettere (maiuscole o minuscole)
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_ireland_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_ireland_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>Italia

Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida di Italia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Lettonia

### <a name="format"></a>Formato

Tre lettere seguite da sei cifre
  
### <a name="pattern"></a>Modello

Tre lettere e sei cifre:
  
-  Tre lettere (maiuscole o minuscole) 
    
- Sei cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_latvia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_latvia_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>Lituania

### <a name="format"></a>Formato

Otto cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 Otto cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_lithuania_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_lithuania_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Lussemburgo

### <a name="format"></a>Formato

Sei cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

 Sei cifre 
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_luxemburg_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_luxemburg_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formato

Combinazione di due caratteri e sei cifre nella serie specificata
  
### <a name="pattern"></a>Modello

Combinazione di due caratteri e sei cifre:
  
- Due caratteri (cifre o lettere maiuscole o minuscole)
    
- Uno spazio (facoltativo)
    
- Tre cifre
    
- Uno spazio (facoltativo)
    
- Tre cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_malta_eu_driver's_license_number` viene trovato. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> attività liċenzja-sewqan  <br/> |
   
## <a name="netherlands"></a>Paesi Bassi

### <a name="format"></a>Formato

10 cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

10 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_netherlands_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_netherlands_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> 
permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>Polonia

### <a name="format"></a>Formato

14 cifre che contiene 2 barre
  
### <a name="pattern"></a>Modello

14 cifre e 2 barre:
  
-  Cinque cifre 
    
- Una barra
    
- Due cifre
    
- Una barra
    
- Sette cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_poland_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_poland_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>Portogallo

### <a name="format"></a>Formato

Due lettere seguite da un sette i numeri in formato specificato
  
### <a name="pattern"></a>Modello

Due lettere seguite da sette numeri con caratteri speciali:
  
-  Due lettere (maiuscole o minuscole) 
    
- Una lineetta
    
- Sei cifre
    
- Uno spazio
    
- Una cifra
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_portugal_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_portugal_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>Romania

### <a name="format"></a>Formato

Un carattere seguito da 8 cifre
  
### <a name="pattern"></a>Modello

Un carattere seguito da 8 cifre:
  
-  Una lettera (maiuscole o minuscole) o cifre 
    
- Otto cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_romania_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_romania_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> permis de conducere  <br/> |
   
## <a name="slovakia"></a>Slovacchia

### <a name="format"></a>Formato

Un carattere seguito da sette cifre
  
### <a name="pattern"></a>Modello

Un carattere seguito da sette cifre
  
- Una lettera (maiuscole o minuscole) o cifre
    
-  Sette cifre 
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovakia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovakia_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>Slovenia

### <a name="format"></a>Formato

Nove cifre senza spazi e i delimitatori
  
### <a name="pattern"></a>Modello

9 cifre
  
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovenia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovenia_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>Spagna

### <a name="format"></a>Formato

Otto cifre seguite da un carattere
  
### <a name="pattern"></a>Modello

Otto cifre seguite da un carattere:
  
-  Otto cifre 
    
- Una cifra o lettere (maiuscole o minuscole)
    
### <a name="checksum"></a>Checksum

Sì
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- La funzione `Func_spain_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_spain_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno #  <br/> DL #  <br/> driver lic.  <br/> titolo driver  <br/> patente  <br/> drivers licence  <br/> 
drivers license  <br/> titolo della patente di Guida  <br/> patente  <br/> driving licence
  <br/> le licenze  <br/> numero della patente del driver  <br/> Numero patente di Guida  <br/> numero di driver di licenza  <br/> Numero patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> Numero patente di Guida  <br/> che influisce sul numero di licenza  <br/> Guida autorizza  <br/> che influisce sul numero permesso  <br/> permiso de conducción  <br/> permiso conducción  <br/> número licencia conducir  <br/> número de carnet de conducir  <br/> número carnet conducir  <br/> licencia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> EL carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>Svezia

### <a name="format"></a>Formato

Dieci cifre che contiene un segno meno
  
### <a name="pattern"></a>Modello

Dieci cifre che contiene un segno meno:
  
-  Sei cifre 
    
- Una lineetta
    
- Quattro cifre
    
### <a name="checksum"></a>Checksum

No
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_sweden_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_sweden_eu_driver's_license_number` viene trovato. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Parole chiave

| |
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|DL #  <br/> patente  <br/> Numero patente di Guida  <br/> titolo driver  <br/> driver lic.  <br/> patente di Guida  <br/> drivers licence  <br/> patente  <br/> numero della patente di Guida  <br/> numero della patente di Guida  <br/> che influisce sul numero di licenza  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>REGNO UNITO

Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida di Regno Unito" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

