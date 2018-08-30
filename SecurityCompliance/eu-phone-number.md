---
title: Numero di telefono dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate numero di telefono dell'Unione europea.
ms.openlocfilehash: 9dd878e3385312982f9f3a4927205e3ebb27aabb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530873"
---
# <a name="eu-phone-number"></a>Numero di telefono dell'Unione europea

Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate numero di telefono dell'Unione europea. 
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Lunghezza non standard
  
### <a name="pattern"></a>Modello

- Cifre 
    
- Solo i numeri di telefono cellulare iniziano con la cifra "6" 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_austria_eu_telephone_number_1` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_austria_eu_telephone_number_2` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_telephone_number` viene trovato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a>Belgio

### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_belgium_eu_telephone_number_1` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_belgium_eu_telephone_number_2` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_telephone_number` viene trovato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## <a name="bulgaria"></a>Bulgaria

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_bulgaria_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_bulgaria_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_bulgaria_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## <a name="croatia"></a>Croazia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_croatia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_croatia_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_croatia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="cyprus"></a>Cipro

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_cyprus_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_cyprus_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_cyprus_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="czech-republic"></a>Repubblica Ceca

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_czech_republic_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_czech_republic_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_czech_republic_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="denmark"></a>Danimarca

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_denmark_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_denmark_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_denmark_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="estonia"></a>Estonia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_estonia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_estonia_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_estonia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="finland"></a>Finlandia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_finland_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_finland_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_finland_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="france"></a>Francia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_france_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_france_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_france_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="germany"></a>Germania

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_germany_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_germany_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_germany_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="greece"></a>Grecia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_greece_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_greece_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_greece_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="hungary"></a>Ungheria

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_hungary_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_hungary_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="ireland"></a>Irlanda

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_ireland_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_ireland_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_ireland_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="italy"></a>Italia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_italy_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_italy_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_italy_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="latvia"></a>Lettonia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_latvia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_latvia_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_latvia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="lithuania"></a>Lituania

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_lithuania_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_lithuania_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_lithuania_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="luxemburg"></a>Lussemburgo

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_luxemburg_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_luxemburg_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_luxemburg_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## <a name="malta"></a>Malta

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_malta_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="netherlands"></a>Paesi Bassi

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_netherlands_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_netherlands_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_netherlands_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="poland"></a>Polonia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_poland_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_poland_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_poland_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="portugal"></a>Portogallo

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_portugal_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_portugal_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_portugal_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="romania"></a>Romania

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_romania_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_romania_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_romania_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovakia"></a>Slovacchia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovakia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovakia_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovakia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovenia"></a>Slovenia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovenia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovenia_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovenia_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="spain"></a>Spagna

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_spain_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_spain_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_spain_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="sweden"></a>Svezia

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_sweden_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_sweden_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_sweden_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="uk"></a>REGNO UNITO

### <a name="pattern"></a>Modello

- Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_uk_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_uk_eu_telephone_number` viene trovato. 
    
Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_uk_eu_telephone_number` consente di trovare contenuto corrispondente al formato. 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

