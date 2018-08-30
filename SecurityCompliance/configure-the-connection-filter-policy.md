---
title: Configurare i criteri di filtro di connessione
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: Per assicurarsi che non è bloccato posta elettronica inviato da mittenti che attendibili, è possibile utilizzare i criteri di filtro di connessione per creare un elenco Consenti, noto anche come un elenco di mittenti attendibili, gli indirizzi IP attendibili. È inoltre possibile creare un elenco di mittenti bloccati.
ms.openlocfilehash: cb9b73ff61b477f1c7ea0bb8da4039bebce83d1b
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003265"
---
# <a name="configure-the-connection-filter-policy"></a>Configurare i criteri di filtro delle connessioni
 
La maggior parte degli Stati Uniti hanno amici e partner commerciali che è attendibile. Può essere frustrante trovare della posta elettronica da loro nella cartella posta indesiderata, o persino bloccato interamente da un filtro posta indesiderata. Se si desidera verificare che non è bloccato posta elettronica inviato da mittenti che attendibili, è possibile utilizzare i criteri di filtro di connessione per creare un elenco Consenti, noto anche come un elenco dei mittenti attendibili, dell'indirizzo IP indirizzi che si desidera considerare attendibile. È inoltre possibile creare un elenco dei mittenti bloccati, che corrisponde a un elenco di indirizzi IP, in genere da noti mittenti di posta indesiderata, che non si desidera ricevere messaggi di posta elettronica, mai.
  
 Per ulteriori impostazioni di posta indesiderata che si applicano a tutta l'organizzazione, esaminare [per contribuire a garantire che un messaggio non è contrassegnato come posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=534224) o di [posta elettronica di blocco della posta indesiderata con il filtro posta indesiderata di Office 365 per evitare problemi negativi false](https://go.microsoft.com/fwlink/p/?LinkId=534225). Questi sono utili se si dispone di controllo a livello di amministratore e si desidera impedire falsi positivi o falsi negativi.
  
Il seguente video mostra i passaggi di configurazione per i criteri del filtro di connessione:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?
<a name="sectionSection0"> </a>

- Tempo stimato per il completamento: 15 minuti
    
- È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
    
- Per ottenere l'indirizzo IP del mittente per il quale vuoi consentire o bloccare i messaggi, puoi guardare l'intestazione Internet del messaggio. Cercare l'intestazione CIP come descritto in [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md). Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere l'argomento [Analizzatore intestazione messaggio](https://go.microsoft.com/fwlink/p/?LinkId=306583). 
    
- Verranno rifiutati i messaggi di posta elettronica inviati da un indirizzo IP nell'elenco indirizzi IP bloccati, non è contrassegnato come posta indesiderata, e si verifica alcun altre opzioni di filtro.
    
- La procedura di filtro di connessione seguente può anche essere eseguita tramite remote PowerShell. Utilizzare il cmdlet [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) per controllare le impostazioni e [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) per modificare le impostazioni di criteri di filtro di connessione. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Utilizzare EAC per modificare il criterio del filtro connessioni predefinito
<a name="sectionSection1"> </a>

Creare un elenco indirizzi IP consentiti o un elenco indirizzi IP bloccati modificando i criteri del filtro di connessione in EAC (Exchange admin center). Le impostazioni dei criteri del filtro connessioni vengono applicati solo ai messaggi in ingresso.
  
1. Nell'interfaccia di amministrazione di Exchange (EAC), accedere a **Protezione** \> **Filtro connessioni**, quindi fare doppio clic sul criterio predefinito.
    
2. Fare clic sulla voce di menu **Filtro connessioni**, quindi creare gli elenchi desiderati: un elenco indirizzi IP consentiti, un elenco indirizzi IP bloccati o entrambi. 
    
    Per creare questi elenchi, fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif). Nella finestra di dialogo successiva, specificare l'indirizzo IP o l'intervallo di indirizzi IP, quindi fare clic su **ok**. Ripetere il processo per aggiungere indirizzi aggiuntivi. È anche possibile modificare o rimuovere gli indirizzi IP dopo averli aggiunti.
    
    > [!NOTE]
    >  Se si aggiunge un indirizzo IP per entrambi gli elenchi, è consentita l'invio della posta. > Gli indirizzi IP IPV4 devono essere specificati in nnn formato dove nnn è un numero compreso tra 0 e 255. È inoltre possibile specificare intervalli IP Classless Inter-Domain Routing (CIDR) in nnn.nnn.nnn.nnn/rr formato dove rr è un numero compreso tra 24 e 32. Per specificare gli intervalli di fuori dell'intervallo di 24-32, vedere [Considerazioni aggiuntive per la configurazione di indirizzi IP consentiti elenchi](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists). > È possibile specificare un massimo di 1273 voci, in cui una voce è un singolo indirizzo IP o un CIDR intervallo di indirizzi IP compreso tra/24 e/32. > Se si inviano messaggi crittografati con TLS, gli intervalli di indirizzi e gli indirizzi IPv6 non sono supportati. 
  
3. Facoltativamente, selezionare la casella di controllo **Abilita elenco sicuro** per impedire mancanti della posta elettronica da determinati mittenti noti. In che modo? Microsoft si abbona a terze parti di mittenti attendibili. Utilizzare questo elenco sicuro significa che queste attendibili i mittenti erroneamente non vengono contrassegnati come posta indesiderata. È consigliabile se si seleziona questa opzione perché consigliabile ridurre il numero di falsi positivi (posta legittima classificata come posta indesiderata) viene visualizzato. 
    
4. Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri predefiniti.
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Ulteriori considerazioni durante la configurazione di elenchi di indirizzi IP consentiti
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

Di seguito sono riportate ulteriori considerazioni cui fare attenzione durante la configurazione di un elenco di indirizzi IP consentiti.
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Specificazione di un intervallo CIDR al di fuori dell'intervallo consigliato

Per specificare un intervallo di indirizzi IP CIDR da /1 a /23, è necessario creare una regola di trasporto che viene applicato l'intervallo di indirizzi IP che imposta il livello di probabilità di posta indesiderata (SCL) al **filtro della posta indesiderata Bypass** (vale a dire che tutti i messaggi ricevuti all'interno di questo intervallo di indirizzi IP sono impostata su "posta non indesiderata? e non altre opzioni di filtro viene eseguita dal servizio). Tuttavia, se uno di questi indirizzi IP visualizzato in qualsiasi del blocco proprietaria di Microsoft sono elencati o in qualsiasi il blocco di terze parti sono elencati, questi messaggi ancora da bloccare. È pertanto consigliabile utilizzare l'intervallo di indirizzi IP /32 a /24. 
  
Per creare una regola di trasporto, eseguire i passaggi seguenti:
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.
    
3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.
    
4. In **Applica la regola se**, selezionare **Il mittente**, quindi scegliere **L'indirizzo IP è in tutti gli intervalli o corrisponde esattamente**.
    
5. In **specificare indirizzi IP**, specificare l'intervallo di indirizzi IP, fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif), quindi su **ok**.
    
6. Nella casella **Effettuare le seguenti operazioni**, impostare l'azione scegliendo **Modificare le proprietà dei messaggi**, quindi **imposta il livello di probabilità di posta indesiderata (SCL)**. Nella casella **specifica SCL**, selezionare **Ignora il filtro di protezione da posta indesiderata**, quindi fare clic su **ok**.
    
7. È possibile effettuare selezioni per controllare, provare e attivare la regola durante un periodo di tempo specifico. Sono disponibili ulteriori selezioni. Si consiglia di provare la regola per un periodo di tempo prima di applicarla. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contiene ulteriori informazioni sulle selezioni. 
    
8. Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole. 
    
Dopo aver creato e applicato la regola, il filtro posta indesiderata viene ignorato per l'intervallo di indirizzi IP specificato.
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Ambito delle eccezioni dell'elenco di indirizzi IP consentiti per un dominio specifico

In generale, si consiglia di aggiungere gli indirizzi IP (o intervalli di indirizzi IP) per tutti i domini considerati sicuri nell'elenco degli indirizzi IP consentiti. Tuttavia, per non applicare la voce Elenco indirizzi IP consentiti a tutti i domini, è possibile creare una regola di trasporto che escluda domini specifici. 
  
Ad esempio, si supponga che vi siano tre domini: ContosoA.com, ContosoB.com e ContosoC.com, e si desideri aggiungere l'indirizzo IP (per semplicità utilizzeremo 1.2.3.4) e ignorare il filtro solo per il dominio ContosoB.com. In questo caso si crea un elenco di indirizzi IP consentiti per 1.2.3.4, che imposta il livello di probabilità di posta indesiderata (SCL) su -1 (indicante che non si tratta di posta indesiderata) per tutti i domini. È possibile quindi creare una regola di trasporto che imposta il livello SCL per tutti i domini eccetto ContosoB.com su 0. In tal modo il messaggio viene riesaminato per tutti i domini associati all'indirizzo IP eccetto che per ContosoB.com, ossia il dominio elencato come eccezione nella regola. ContosoB.com ha un SCL impostato su -1, quindi il filtro viene ignorato, mentre ContosoA.com e ContosoC.com hanno un SCL impostato su 0, quindi per essi viene applicato il filtro contenuto.
  
A tale scopo, eseguire la procedura seguente:
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.
    
3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.
    
4. In **Applica la regola se**, selezionare **Il mittente**, quindi scegliere **L'indirizzo IP è in tutti gli intervalli o corrisponde esattamente**.
    
5. Nella casella **specifica gli indirizzi IP**, specificare l'indirizzo o l'intervallo di indirizzi IP immesso nell'elenco di indirizzi IP consentiti, fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e scegliere **ok**.
    
6. In **Effettuare le seguenti operazioni**, impostare l'azione scegliendo **Modificare le proprietà dei messaggi**, quindi **imposta il livello di probabilità di posta indesiderata (SCL)**. Nella casella **specifica SCL**, selezionare **0**, quindi fare clic su **ok**.
    
7. Fare clic su **aggiungi eccezione** e in **Tranne se**, selezionare **Il mittente** e scegliere **il dominio è**. 
    
8. Nella casella **specifica dominio**, immettere il dominio per il quale si desidera ignorare il filtro posta indesiderata, ad esempio **contosob.com**. Fare clic su **Aggiungi**![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) per spostarlo nell'elenco di frasi. Ripetere la procedura per aggiungere ulteriori domini come eccezioni e fare clic su **ok** una volta terminato. 
    
9. È possibile effettuare selezioni per controllare, provare e attivare la regola durante un periodo di tempo specifico. Sono disponibili ulteriori selezioni. Si consiglia di provare la regola per un periodo di tempo prima di applicarla. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contiene ulteriori informazioni sulle selezioni. 
    
10. Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole. 
    
Dopo aver creato e applicato la regola, il filtro posta indesiderata per l'indirizzo o l'intervallo di indirizzi IP specificato viene ignorato solo per l'eccezione di dominio immessa.
  
## <a name="new-to-office-365"></a>Nuovo utente di Office 365?
<a name="sectionSection3"> </a>

||
|:-----|
|![Piccola icona per LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning. |
   
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection4"> </a>

[Elenchi di mittenti attendibili e bloccati in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
[Configurazione del criterio delle posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Come assicurarsi che un messaggio non venga contrassegnato come indesiderato](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

