---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: Eliminazione automatica zero ore (ZAP) è una funzionalità di protezione posta elettronica in grado di rilevare i messaggi con la posta indesiderata o malware che sono già stati consegnati alla posta in arrivo degli utenti e quindi viene eseguito il rendering del contenuto dannoso dannosa. Come ZAP esegue questa operazione dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: dabe4caf8916d3f0de7a70cb3d056dd9a7fdcc3f
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857244"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware

Eliminazione automatica zero ore (ZAP) è una funzionalità di protezione posta elettronica in grado di rilevare i messaggi con la posta indesiderata o malware che sono già stati consegnati alla posta in arrivo degli utenti e quindi viene eseguito il rendering del contenuto dannoso dannosa. Come ZAP esegue questa operazione dipende dal tipo di contenuto dannoso rilevato.
  
ZAP è disponibile con l'impostazione predefinita, Exchange Online Protection incluso in qualsiasi sottoscrizione a Office 365 che contiene le cassette postali di Exchange Online.
  
## <a name="how-does-zap-work"></a>Funzionamento ZAP

Aggiornamenti di Office 365 firme malware e motore di protezione da posta indesiderate in tempo reale a intervalli giornalieri. Gli utenti possono comunque dannoso messaggi vengano recapitati posta in arrivo per una serie di motivi, tra cui quando il contenuto è stato weaponized alla volta dopo che è stato innanzitutto inviato agli utenti. ZAP indirizzi questo monitorando continuamente viene aggiornata per le firme di posta indesiderata e malware Office 365, e pertanto individuare e rimuovere già contenuti ai messaggi di posta in arrivo. Per la posta che è già stata identificata come posta indesiderata, ZAP Sposta i messaggi non letti nella cartella posta indesiderata dell'utente. Per appena rilevato malware, ZAP rimuove gli allegati dal messaggio di posta elettronica, indipendentemente dal fatto che la posta elettronica è stato letto o non. È invece per i messaggi che sono stati classificati in modo non corretto come dannose.
  
L'azione ZAP è semplice per la cassetta postale utente potrà non riceve una notifica che di posta elettronica è stato spostato.
  
Consenti regole degli utenti finali, [regole del flusso di posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=722755)e gli elenchi o altri filtri hanno la precedenza su ZAP.
  
 **Contenuto dell'articolo**
  
> [Impostare i criteri di filtro posta indesiderata](zero-hour-auto-purge.md#BK_SetSpam)
    
> [Vedere se ZAP spostato il messaggio](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [Disabilitare ZAP](zero-hour-auto-purge.md#BK_Posh)
    
> [Domande frequenti](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a>Utilizzo di ZAP

ZAP è attivata per impostazione predefinita, ma è necessario assicurarsi che siano soddisfatti due condizioni:
  
- Criterio di filtro posta indesiderata è impostata su [spostare il messaggio nella cartella posta indesiderata](zero-hour-auto-purge.md#BK_SetSpam).
    
    È inoltre possibile creare un nuovo criterio di filtro posta indesiderata che si applica solo a un insieme di utenti se non si desidera che tutte le cassette postali per essere analizzata da ZAP.
    
- L'utente [Opzioni \> posta indesiderata](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F).
    
Se si desidera [visualizzare se ZAP spostato il messaggio](zero-hour-auto-purge.md#BK_DidZAPMove), è possibile utilizzare lo strumento di traccia messaggio Exchange Online.
  
Gli amministratori inoltre possono [disabilitare ZAP](zero-hour-auto-purge.md#BK_Posh) tramite PowerShell. 
  
 **Per impostare il criterio di filtro posta indesiderata**
  
1. Accedere al [percorso di accesso a Office 365 per aziende](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) e fare clic su **protezione** \> **Filtro posta indesiderata**. 
    
    ![In EAC selezionare protezione e quindi Filtro posta indesiderata](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. Scegliere il criterio di filtro che si desidera modificare, oppure scegliere **Aggiungi**![sull'icona Aggiungi](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) per crearne uno nuovo. 
    
    Nella schermata precedente, il criterio è denominato "Default", ma se si creano spam ulteriori criteri di filtro è possibile fornire loro un nome diverso. È anche possibile applicare il criterio a un set limitato di utenti.
    
3. Nella finestra criteri, scegliere **azioni per la posta indesiderata e blocco**e verificare che **la posta indesiderata** è impostata su **Sposta il messaggio nella cartella posta indesiderata**. 
    
    Se si sceglie **Salva** a questo punto, il criterio viene applicato al tenant di Office 365. 
    
    ![Impostare la posta indesiderata e azioni per sposta il messaggio nella cartella posta indesiderata in blocco](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. Se è stato creato un nuovo criterio e si desidera applicare il criterio a solo un set di utenti, scorrimento nella finestra del filtro dei criteri e i controlli di menu nella sezione **Applicato a** scegliere i **destinatari**, **dominio**o **appartenenze a gruppi** è Se si desidera applicare il criterio. È inoltre possibile impostare eccezioni e le altre. 
    
    ![Nella sezione applicata per scegliere i destinatari](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    Scegliere **Salva** per applicare il criterio agli utenti selezionati. 
    
 **Per vedere se ZAP spostato il messaggio**
  
- È possibile utilizzare per determinare se il messaggio è stato spostato dal ZAP [individuare e risolvere i problemi di recapito di posta elettronica come un amministratore aziendale di Office 365](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) : 
    
    Cercare il testo "ora Zero automatico di eliminazione (ZAP)" le informazioni di traccia per identificare un messaggio in cui è stato spostato dal ZAP.
    
 **Per disabilitare ZAP**
  
- Se si desidera disabilitare ZAP per il tenant di Office 365 o un insieme di utenti, utilizzare il parametro **ZapEnabled** del [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet EOP.
    
    Nell'esempio seguente, ZAP è disabilitata per un criterio di filtro dei contenuti denominato "Test".
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a>Domande frequenti
<a name="BK_FAQ"> </a>

 **Cosa succede se un messaggio viene spostato nella cartella posta indesiderata?**
  
È consigliabile eseguire il normale processo di creazione di rapporti per falsi positivi. È l'unico motivo il messaggio verrà spostato dalla posta in arrivo nella cartella posta indesiderata in quanto il servizio ha rilevato che il messaggio era posta indesiderata o dannosi.
  
 **Se è possibile utilizzare alla quarantena di Office 365 anziché nella cartella posta indesiderata?**
  
ZAP non vengono spostati i messaggi in quarantena dalla posta in arrivo in questa fase.
  
 **Se dispone di una regola di flusso di posta personalizzato (bloccare o consentire regola)?**
  
Le regole create da admins (regole del flusso di posta elettronica) o Consenti e blocca regole hanno la precedenza. Tali messaggi vengono esclusi dai criteri di funzionalità.
  
## <a name="related-topics"></a>Argomenti correlati
<a name="BK_FAQ"> </a>

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](block-email-spam-to-prevent-false-negatives.md)
  

