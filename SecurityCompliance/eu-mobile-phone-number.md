---
title: Numero di cellulare UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate dell'Unione europea numero di cellulare.
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530705"
---
# <a name="eu-mobile-phone-number"></a>Numero di cellulare UE

Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate dell'Unione europea numero di cellulare. 
  
## <a name="austria"></a>Austria

### <a name="format"></a>Formato

Cifre senza le lunghezze standard
  
### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_austria_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_austria_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_austria_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a>Belgio

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_belgium_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_belgium_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_belgium_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a>Bulgaria

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_bulgaria_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_bulgaria_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_bulgaria_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a>Croazia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_croatia_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_croatia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_croatia_eu_mobile_number` viene trovato. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a>Cipro

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_cyprus_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_cyprus_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_cyprus_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a>Repubblica Ceca

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_czech_republic_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_czech_republic_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_czech_republic_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a>Danimarca

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_denmark_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_denmark_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_denmark_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a>Estonia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_estonia_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_estonia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_estonia_eu_mobile_number` viene trovato. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a>Finlandia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_finland_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_finland_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_finland_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a>Francia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_france_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_france_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_france_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a>Germania

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_germany_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_germany_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_germany_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a>Grecia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_greece_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_greece_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_greece_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a>Ungheria

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_hungary_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_hungary_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_hungary_eu_mobile_number` viene trovato. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a>Irlanda

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_ireland_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_ireland_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_ireland_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a>Italia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_italy_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_italy_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_italy_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a>Lettonia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_latvia_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_latvia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_latvia_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a>Lituania

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_lithuania_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_lithuania_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_lithuania_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a>Lussemburgo

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_luxumburg_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_luxumburg_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_luxumburg_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a>Malta

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_malta_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_malta_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_malta_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a>Paesi Bassi

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_netherlands_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_netherlands_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_netherlands_eu_mobile_number` viene trovato. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a>Polonia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_poland_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_poland_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_poland_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a>Portogallo

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_portugal_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_portugal_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_portugal_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a>Romania

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_romania_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_romania_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_romania_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a>Slovacchia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovakia_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_slovakia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovakia_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a>Slovenia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_slovenia_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_slovenia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_slovenia_eu_mobile_number` viene trovato. 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a>Spagna

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_spain_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_spain_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_spain_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a>Svezia

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_sweden_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_sweden_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_sweden_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a>REGNO UNITO

### <a name="pattern"></a>Modello

-  Cifre 
    
### <a name="checksum"></a>Checksum

Non applicabile
  
### <a name="definition"></a>Definizione

Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:
  
- L'espressione regolare `Regex_uk_eu_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- L'espressione regolare `Regex_uk_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato. 
    
- Una parola chiave da `Keywords_uk_eu_mobile_number` viene trovato. 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a>Vedere anche

[Cosa individuano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)

