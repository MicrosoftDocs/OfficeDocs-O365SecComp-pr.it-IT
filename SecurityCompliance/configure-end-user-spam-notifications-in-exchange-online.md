---
title: Configurazione di notifiche di posta indesiderata in Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: È possibile configurare le notifiche di posta indesiderata degli utenti finali per il criterio di filtro del contenuto a livello dell'azienda o per i criteri di filtro del contenuto personalizzati applicati ai domini.
ms.openlocfilehash: e29cc850b7f91ed4ec963a8e52e40a0044fa7f6c
ms.sourcegitcommit: 234a22c61859133ed5e7988a9551a569781518a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23875808"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurazione di notifiche di posta indesiderata in Exchange Online

> [!IMPORTANT]
> In questo argomento è per i clienti di Exchange Online che desidera proteggere le cassette postali ospitate nel cloud. I clienti autonomo di Exchange Online Protection (EOP) che sono protezione cassette postali locali è consigliabile leggere l'argomento seguente invece: [Configura notifiche di posta indesiderata in EOP](configure-end-user-spam-notifications-in-eop.md). 
  
È possibile configurare le notifiche di posta indesiderata degli utenti finali per il criterio di filtro del contenuto a livello dell'azienda o per i criteri di filtro del contenuto personalizzati applicati ai domini. L'abilitazione dei messaggi di notifica di posta indesiderata per l'utente finale consente agli utenti di gestire autonomamente i messaggi di posta indesiderata messi in quarantena. Le notifiche di posta indesiderata dell'utente finale non possono essere utilizzate con criteri applicati a utenti o gruppi o a un criterio con eccezioni.
  
Le notifiche di posta indesiderata dell'utente finale contengono un elenco di tutti i messaggi di posta indesiderata messi in quarantena ricevuti dall'utente finale durante un periodo di tempo configurato. È possibile specificare un valore compreso tra 1 e 15 giorni. È inoltre possibile configurare la lingua in cui è scritto il messaggio di notifica.
  
Dopo aver ricevuto un messaggio di notifica, gli utenti finali possono scegliere tra le opzioni seguenti:

**Anteprima** messaggio se si desidera visualizzare in anteprima il contenuto o l'intestazione prima dell'esecuzione di azioni.

**Scaricare** il messaggio se si desidera esaminare i messaggi e allegati (se esistenti) del dispositivo prima dell'esecuzione di azioni.

**Versione** se non è il messaggio di posta indesiderata e si vuole che Office 365 per inviare il messaggio alla cassetta postale.

**Versione e consentire mittente** se non è il messaggio di posta indesiderata e si vuole che Office 365 per aggiungere il mittente per i mittenti attendibili e l'elenco di destinatari per messaggi di posta elettronica futuri. Tenere presente che l'amministratore può essere altre configurazioni di Consenti e blocca ampia organizzazione che sostituire l'elenco dei mittenti attendibili.

**Versione & rapporto**, se non è il messaggio di posta indesiderata e si desidera inviare il messaggio alla cassetta postale e segnalare a Microsoft per l'analisi.

**Blocco** se si desidera che Office 365 per aggiungere il mittente all'elenco Mittenti bloccati.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento: 2 minuti
  
È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per la configurazione delle notifiche di posta indesiderata

1. Nell'interfaccia di amministrazione di Exchange (EAC), andare a **Protezione**\> **Filtro contenuto**.
    
2. Selezionare il filtro contenuto per cui si desidera abilitare le notifiche di posta indesiderata dell'utente finale, che sono disabilitate per impostazione predefinita.
    
3. Nel riquadro di destra, in cui sono contenute informazioni di riepilogo sul criterio, fare clic sul collegamento **Configura notifiche spam utente finale**. 
    
4. Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:
    
1. **Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio. 
    
2. **Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata. 
    
3. **Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione. 
    
5. Fare clic su **Salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni del criterio di filtro del contenuto, incluse quelle relative alle notifiche di posta indesiderata dell'utente finale.
    
> [!NOTE]
>  Le notifiche di posta indesiderata dell'utente finale saranno applicate solo ai criteri filtro del contenuto abilitati. >  Le notifiche di posta indesiderata dell'utente finale vengono inviate solo una volta al giorno. Non è possibile garantire l'ora di recapito della notifica per alcun utente specifico e non è possibile configurarla. 
  
 **Suggerimento:** prima di implementare le notifiche di posta indesiderata, è possibile sottoporle a test inviandole a gruppo limitato di utenti finali. A tale scopo, è possibile creare un criterio di filtro dei contenuti personalizzato che consenta di abilitare le notifiche di posta indesiderate per i domini dell'utente finale. A questo punto, nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta \> regole**, creare una regola di trasporto per bloccare i messaggi provenienti da quarantine@messaging.microsoft.com (indirizzo da cui vengono inviate le notifiche), escludendo gli utenti che desiderano ricevere tali notifiche. La figura seguente descrive un esempio relativo alla creazione di un'eccezione per due utenti (SaraD e AlexD) dal dominio Contoso.com: 
  
![Regola di trasporto per verificare le notifiche di posta indesiderata dell'utente finale](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
