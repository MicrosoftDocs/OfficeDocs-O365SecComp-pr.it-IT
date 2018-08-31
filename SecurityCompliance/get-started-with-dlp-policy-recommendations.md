---
title: Introduzione ai suggerimenti per i criteri di prevenzione della perdita dei dati
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2ea4459b-cb13-4ce2-b9d1-0619316df88c
description: Questo suggerimento basati su conoscenze consente all'organizzazione di proteggere contenuti sensibili quando sono archiviate e condivise in Office 365 da per informare l'utente quando esiste una distanza possibile in copertura il criterio DLP. Questo suggerimento verrà visualizzato nella Home page della sicurezza &amp; centro conformità, se i documenti contengano uno dei tipi principali cinque più comuni di informazioni riservate, ma non sono protetti da un criterio DLP.
ms.openlocfilehash: 842387397b9b95d236660c5809174c2b356cf14a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531345"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>Introduzione ai suggerimenti per i criteri di prevenzione della perdita dei dati

Questo suggerimento basati su conoscenze consente all'organizzazione di proteggere contenuti sensibili quando sono archiviate e condivise in Office 365 da per informare l'utente quando esiste una distanza possibile in copertura il criterio DLP. Questo suggerimento verrà visualizzato nella Home **page della sicurezza** &amp; centro conformità, se i documenti includono i tipi più comuni di cinque principali di informazioni riservate, ma non sono protetti da un criterio di criterio DLP perdita di dati. 
  
È possibile utilizzare questo widget per creare rapidamente un criterio DLP personalizzato in un semplice clic o due e dopo aver creato il criterio DLP, è completamente personalizzabile. Si noti che se non viene visualizzata l'indicazione inizialmente, provare a fare clic su **+ più** nella parte inferiore della sezione **consigliato è** . 
  
![Widget denominato informazioni riservate non protette](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>Creare il criterio DLP consigliato

Quando il widget Visualizza che protetta informazioni riservate, scegliere **Introduzione** nella parte inferiore per creare rapidamente un criterio DLP. 
  
Per proteggere le informazioni riservate, il criterio DLP:
  
- Rileva quando il contenuto di Exchange, SharePoint e OneDrive che contiene uno dei tipi di informazioni riservate non protetti è condivise con utenti esterni all'organizzazione.
    
- Genera rapporti dettagliati attività in modo che è possibile tenere traccia di elementi quali il contenuto che ha condiviso con persone esterne all'organizzazione e quando avveniva. È possibile utilizzare i [rapporti DLP](view-the-dlp-reports.md) e [i dati del Registro di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività** = **DLP**) per visualizzare queste informazioni.
    
È anche possibile scegliere di criteri DLP:
  
- Inviare un messaggio di posta elettronica rapporto operazioni non consentite quando gli utenti di condividere una quantità elevata di informazioni sensibili con persone esterne all'organizzazione.
    
- Aggiungere altri utenti per il rapporto operazioni non consentite di posta elettronica.
    
- Mostra un suggerimento sul criterio e inviare una notifica tramite posta elettronica agli utenti che tentano di condividere le informazioni sensibili con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti sui criteri per i criteri DLP](use-notifications-and-policy-tips.md).
    
Se si desidera modificare in seguito queste opzioni, è possibile modificare il criterio DLP dopo averlo creato. Ad esempio, è possibile effettuare il criterio più restrittivo da utenti anche blocco dalla condivisione di contenuto che contiene informazioni riservate in primo luogo, vedere la sezione successiva.
  
![Le impostazioni per il widget denominato informazioni riservate non protette](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>Modificare il criterio DLP consigliato

Dopo aver utilizzato il widget per creare un criterio DLP, il criterio viene visualizzato in **prevenzione della perdita di dati** nella pagina **criteri** di sicurezza &amp; centro conformità. 
  
Per impostazione predefinita, il criterio è denominato **Criterio consigliato di sistema per la condivisione di informazioni riservate**. Questo criterio è completamente personalizzabile e lo stesso qualsiasi criterio DLP è creati dall'utente da zero. Ad esempio, se deciso di non attivare rapporti operazioni non consentite e suggerimenti sui criteri quando si utilizza il widget, possono sempre modificare i criteri e attivare le opzioni in qualsiasi momento.
  
![Sistema consigliato i criteri per la condivisione delle informazioni riservate](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando il widget e non viene visualizzato

Widget denominato **Informazioni riservate non protette** visualizzata nella sezione **consigliato è** di **Home** page della sicurezza &amp; centro conformità. 
  
Questo widget viene visualizzata solo se:
  
- Nuovi documenti che contiene uno dei cinque tipi più comuni di informazioni riservate vengono rilevati in SharePoint o OneDrive negli ultimi 30 giorni.
    
- Tali informazioni riservate non è già protetto tramite un criterio DLP esistente.
    
A differenza di criteri DLP sono costantemente analisi dei dati, questo suggerimento analizza delle interruzioni nella copertura criterio DLP circa ogni 48 ore, in modo dopo aver caricato il nuovo contenuto, potrebbe richiedere fino a due giorni per il suggerimento venga visualizzata.
  
Infine, dopo aver utilizzato il widget per creare un criterio DLP consigliato, il widget viene eliminata dalla **Home** page di. 
  

