---
title: Introduzione ai criteri di prevenzione della perdita dei dati predefiniti
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: Prima di creare anche il primo criterio di criterio DLP perdita di dati, DLP aiuta a proteggere le informazioni sensibili con un criterio predefinito. Questo criterio predefinito e il relativo Mantieni Guida recommendation (come illustrato di seguito) il contenuto riservato sicuro ricevere una notifica quando il numero di carta di posta elettronica o documenti che contengono un credito sono condivise con una persona esterna all'organizzazione.
ms.openlocfilehash: 1b522a2c04e72353970ef5dfcd62183023a01994
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531463"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introduzione ai criteri di prevenzione della perdita dei dati predefiniti

Prima di creare anche il primo criterio di criterio DLP perdita di dati, DLP aiuta a proteggere le informazioni sensibili con un criterio predefinito. Questo criterio predefinito e il relativo Mantieni Guida recommendation (come illustrato di seguito) il contenuto riservato sicuro ricevere una notifica quando il numero di carta di posta elettronica o documenti che contengono un credito sono condivise con una persona esterna all'organizzazione. Questo suggerimento verrà visualizzato nella Home **page della sicurezza** &amp; centro conformità. 
  
È possibile utilizzare questo widget per visualizzare rapidamente i tempi e la quantità di informazioni sensibili deve essere stato condiviso e quindi ridefinire il criterio DLP predefinito un semplice clic o due. È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile. Si noti che se non viene visualizzata l'indicazione inizialmente, provare a fare clic su **+ più** nella parte inferiore della sezione **consigliato è** . 
  
![Widget denominato per proteggere il contenuto condiviso](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Visualizzare il report e ridefinire il criterio DLP predefinito

Quando il widget viene indicato che gli utenti sono condivisi informazioni riservate con persone esterne all'organizzazione, selezionare **criterio DLP perfezionare** nella parte inferiore. 
  
Il rapporto dettagliato viene illustrato come e quando quantità di contenuto che contiene numeri di carta di credito deve essere stato condiviso negli ultimi 30 giorni. Si noti che corrispondenze alla regola possono richiedere fino a 48 ore possa essere visualizzata nel widget.
  
Per proteggere le informazioni riservate, il criterio DLP predefinito:
  
- Rileva quando il contenuto di Exchange, SharePoint e OneDrive che contiene il numero di carta di credito almeno un è condivise con utenti esterni all'organizzazione.
    
- Visualizza un suggerimento sul criterio e invia una notifica tramite posta elettronica per gli utenti che tentano di condividere le informazioni sensibili con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti sui criteri per i criteri DLP](use-notifications-and-policy-tips.md).
    
- Genera rapporti dettagliati attività in modo che è possibile tenere traccia di elementi quali il contenuto che ha condiviso con persone esterne all'organizzazione e quando avveniva. È possibile utilizzare i [rapporti DLP](view-the-dlp-reports.md) e [i dati del Registro di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività** = **DLP**) per visualizzare queste informazioni.
    
Per perfezionare rapidamente il criterio DLP predefinito, è possibile scegliere di fare in modo che:
  
- Inviare un messaggio di posta elettronica rapporto operazioni non consentite quando gli utenti di condividere informazioni sensibili con persone esterne all'organizzazione.
    
- Aggiungere altri utenti per il rapporto operazioni non consentite di posta elettronica.
    
- Bloccare l'accesso al contenuto che contiene informazioni riservate, ma consentire all'utente di eseguire l'override e condividere o se si desidera inviare.
    
Per ulteriori informazioni su rapporti operazioni non consentite o la limitazione dell'accesso, vedere [Panoramica di criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md).
  
Se si desidera modificare in seguito queste opzioni, è possibile modificare l'impostazione predefinita il criterio DLP in qualsiasi momento, vedere la sezione successiva.
  
![Le impostazioni per widget denominato per proteggere il contenuto condiviso](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Modificare il criterio DLP predefinito

Questo criterio è denominato **criterio predefinito Office 365 DLP** e viene visualizzato sotto **prevenzione della perdita di dati** nella pagina **criteri** di sicurezza &amp; centro conformità. 
  
Questo criterio è completamente personalizzabile e lo stesso qualsiasi criterio DLP è creati dall'utente da zero. È anche possibile disattivare o eliminare il criterio, in modo che gli utenti non sono più ricevano suggerimenti sui criteri o le notifiche di posta elettronica.
  
![Il criterio DLP denominato criterio predefinito DLP di Office 365](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando il widget e non viene visualizzato

Widget denominato **proteggere ulteriormente il contenuto condiviso** visualizzata nella sezione **consigliato è** di **Home** page della sicurezza &amp; centro conformità. 
  
Questo widget viene visualizzata solo se:
  
- Non esistono criteri di prevenzione della perdita di dati nella protezione &amp; centro conformità o interfaccia di amministrazione di Exchange. Questo widget devono utili per iniziare a utilizzare DLP, in modo che non viene visualizzato se si dispone già di criteri DLP.
    
- Il contenuto che include almeno una carta di credito è stato condiviso con una persona esterna all'organizzazione negli ultimi 30 giorni.
    
Si noti che corrispondenze alla regola possono richiedere fino a 48 ore sia disponibile per il widget, in modo dopo il rilevamento di informazioni riservate condivise esternamente, potrebbe richiedere fino a due giorni per il suggerimento venga visualizzata.
  
Infine, dopo aver utilizzato il widget per perfezionare il criterio DLP predefinito, widget viene eliminata dalla **Home** page. 
  

