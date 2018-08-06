---
title: Configurazione di notifiche di posta indesiderata in Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro da posta indesiderata a livello aziendale predefinito o per i criteri di filtro posta indesiderata personalizzati che vengono applicati ai domini.
ms.openlocfilehash: 4a4c7c6b139fe0f8b0a1f6b69c1b95e321293af5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027533"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurazione di notifiche di posta indesiderata in Exchange Online

> [!IMPORTANT]
> In questo argomento è per i clienti di Exchange Online che desidera proteggere le cassette postali ospitate nel cloud. I clienti autonomo di Exchange Online Protection (EOP) che sono protezione cassette postali locali è consigliabile leggere l'argomento seguente invece: [Configura notifiche di posta indesiderata in EOP](configure-end-user-spam-notifications-in-eop.md). 
  
È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro da posta indesiderata a livello aziendale predefinito o per i criteri di filtro posta indesiderata personalizzati che vengono applicati ai domini. Abilitazione di messaggi di notifica di posta indesiderata dell'utente finale consente agli utenti finali di gestire autonomamente i propri messaggi nella quarantena della posta indesiderata. Notifiche di posta indesiderata non possono essere utilizzate con i criteri applicati a utenti o gruppi o a un criterio con le eccezioni.
  
Le notifiche di posta indesiderata dell'utente finale contengono un elenco di tutti i messaggi di posta indesiderata messi in quarantena ricevuti dall'utente finale durante un periodo di tempo configurato. È possibile specificare un valore compreso tra 1 e 15 giorni. È inoltre possibile configurare la lingua in cui è scritto il messaggio di notifica.
  
Dopo aver ricevuto un messaggio di notifica, gli utenti finali possono fare clic per spostare il messaggio di posta elettronica da posta indesiderata in posta in arrivo o la posta indesiderata di posta elettronica come non indesiderato, nel qual caso il rapporto verrà inviato al Team di analisi della posta indesiderata di Microsoft. 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento: 2 minuti
  
È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per la configurazione delle notifiche di posta indesiderata

1. In Interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Filtro posta indesiderata**.
    
2. Selezionare il criterio di filtro posta indesiderata per il quale si desidera abilitare le notifiche di posta indesiderata dell'utente finale (che sono disabilitate per impostazione predefinita).
    
3. Nel riquadro di destra, in cui sono contenute informazioni di riepilogo sul criterio, fare clic sul collegamento **Configura notifiche spam utente finale**. 
    
4. Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:
    
1. **Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio. 
    
2. **Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata. 
    
3. **Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione. 
    
5. Fare clic su **Salva**. Riepilogo delle impostazioni di criteri filtro posta indesiderata, incluse le impostazioni di notifica di posta indesiderata dell'utente finale, viene visualizzato nel riquadro destro.
    
> [!NOTE]
>  Notifiche di posta indesiderata dell'utente finale saranno applicate solo per i criteri di filtro posta indesiderata sono abilitati. > Notifiche di posta indesiderata vengono inviate solo una volta al giorno. I tempi di consegna della notifica non possono essere garantito per un cliente specifico e non sono configurabili. 
  
 **Suggerimento:** Se si desidera testare notifiche di posta indesiderata mediante l'invio di un set limitato di utenti prima di implementarle completamente, creare un criterio di filtro posta indesiderata personalizzati che consente di notifiche di posta indesiderata per i domini in cui risiedono gli utenti. Quindi, in EAC, in **flusso di posta \> regole**, creare una regola di trasporto per bloccare i messaggi da quarantine@messaging.microsoft.com, l'indirizzo di posta elettronica che invia le notifiche, con le eccezioni per gli utenti che si desidera ricevere la notifica. Nell'immagine seguente è riportato un esempio di creazione di un'eccezione di due utenti (SaraD e AlexD) dal dominio Contoso.com: 
  
![Regola di trasporto per verificare le notifiche di posta indesiderata dell'utente finale](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
