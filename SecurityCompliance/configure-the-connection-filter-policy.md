---
title: Configurare il criterio di filtro delle connessioni
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: Per assicurarsi che la posta elettronica inviata da persone di cui si ha fiducia non sia bloccata, è possibile utilizzare i criteri di filtro delle connessioni per creare un elenco di indirizzi conSentiti, noto anche come elenco dei mittenti attendibili, di indirizzo IP attendibile. È inoltre possibile creare un elenco di mittenti bloccati.
ms.openlocfilehash: 2b6cbb709eec6911e8aa83d560d5c00ad2a6e344
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341607"
---
# <a name="configure-the-connection-filter-policy"></a>Configurare i criteri di filtro delle connessioni
 
La maggior parte di noi ha amici e partner commerciali di cui siamo fiduciosi. Può essere frustrante trovare messaggi di posta elettronica dalla cartella posta indesiderata o addirittura essere completamente bloccati da un filtro di posta indesiderata. Se si desidera verificare che la posta elettronica inviata da persone attendibili non sia bloccata, è possibile utilizzare i criteri di filtro delle connessioni per creare un elenco di indirizzi conSentiti, noto anche come elenco dei mittenti attendibili, di indirizzo IP attendibile. È inoltre possibile creare un elenco di mittenti bloccati, che è un elenco di indirizzi IP, in genere da spammer noti, di cui non si desidera mai ricevere messaggi di posta elettronica.
  
 Per ulteriori informazioni sulle impostazioni di posta indesiderata che si applicano all'intera organizzazione, vedere [come garantire che un messaggio non venga contrassegnato come posta](https://go.microsoft.com/fwlink/p/?LinkId=534224) indesiderata o [blocca la posta indesiderata con il filtro di posta indesiderata di Office 365 per evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225). Questi sono utili se si dispone di un controllo a livello di amministratore e si desidera impedire falsi positivi o falsi negativi.
  
Il seguente video mostra i passaggi di configurazione per i criteri del filtro di connessione:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?
<a name="sectionSection0"> </a>

- Tempo stimato per completare la procedura: 15 minuti
    
- Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere "protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
    
- Per ottenere l'indirizzo IP del mittente di cui si desidera consentire o bloccare i messaggi, è possibile controllare l'intestazione Internet del messaggio. Cercare l'intestazione CIP come descritto nelle [intestazioni dei messaggi](anti-spam-message-headers.md)di protezione dalla posta indesiderata. Per informazioni su come visualizzare l'intestazione di un messaggio in vari client di posta elettronica, vedere [message header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583). 
    
- I messaggi di posta elettronica inviati da un indirizzo IP dell'elenco indirizzi IP bloccati vengono rifiutati, non contrassegnati come posta indesiderata e non si verifica alcun filtro aggiuntivo.
    
- La seguente procedura del filtro di connessione può essere eseguita anche tramite Remote PowerShell. Utilizzare il cmdlet [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) per rivedere le impostazioni e [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) per modificare le impostazioni dei criteri di filtro delle connessioni. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [connessione a Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Utilizzare EAC per modificare il criterio del filtro connessioni predefinito
<a name="sectionSection1"> </a>

Creare un elenco indirizzi IP consentiti o un elenco indirizzi IP bloccati modificando i criteri del filtro di connessione in EAC (Exchange admin center). Le impostazioni dei criteri del filtro connessioni vengono applicati solo ai messaggi in ingresso.
  
1. Nell'interfaccia di amministrazione di Exchange (EAC), accedere a **Protezione** \> **Filtro connessioni**, quindi fare doppio clic sul criterio predefinito.
    
2. Fare clic sulla voce di menu **Filtro connessioni**, quindi creare gli elenchi desiderati: un elenco indirizzi IP consentiti, un elenco indirizzi IP bloccati o entrambi. 
    
    Per creare questi elenchi, fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif). Nella finestra di dialogo successiva, specificare l'indirizzo IP o l'intervallo di indirizzi IP, quindi fare clic su **ok**. Ripetere il processo per aggiungere indirizzi aggiuntivi. È anche possibile modificare o rimuovere gli indirizzi IP dopo averli aggiunti.
    
    > [!NOTE]
    >  Se si aggiunge un indirizzo IP ad entrambi gli elenchi, i messaggi di posta elettronica inviati da tale indirizzo IP sono consentiti. 

    Specificare gli indirizzi IP IPV4 nel formato nnn. nnn. nnn. nnn dove nnn è un numero compreso tra 0 e 255. È inoltre possibile specificare gli intervalli CIDR (Inter-Domain Routing) nel formato nnn. nnn. nnn. nnn/RR dove RR è un numero compreso tra 24 e 32. Per specificare gli intervalli all'esterno dell'intervallo da 24 a 32, vedere [ulteriori considerazioni quando](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)si configurano gli elenchi di indirizzi IP consentiti. 

    È possibile specificare un massimo di 1273 voci, in cui una voce è un singolo indirizzo IP o un intervallo CIDR di indirizzi IP compreso tra/24 e/32. > se si inviano messaggi crittografati con TLS, gli indirizzi e gli intervalli di indirizzi IPv6 non sono supportati. 
  
3. Facoltativamente, selezionare la casella di controllo **Abilita elenco sicuro** per evitare che la posta elettronica mancante venga inviata da alcuni mittenti noti. Come? Microsoft sottoscrive le origini di terze parti di mittenti attendibili. L'utilizzo di questo elenco sicuro indica che questi mittenti attendibili non sono stati contrassegnati per la posta indesiderata. Si consiglia di selezionare questa opzione perché dovrebbe ridurre il numero di falsi positivi (una buona posta che è classificata come posta indesiderata) che si riceve. 
    
4. Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri predefiniti.
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Ulteriori considerazioni durante la configurazione di elenchi di indirizzi IP consentiti
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

Di seguito sono riportate ulteriori considerazioni cui fare attenzione durante la configurazione di un elenco di indirizzi IP consentiti.
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Specificazione di un intervallo CIDR al di fuori dell'intervallo consigliato

Per specificare un intervallo di indirizzi IP CIDR da/1 a/23, è necessario creare una regola del flusso di posta che opera nell'intervallo di indirizzi IP che imposta il livello di probabilità di posta indesiderata per **ignorare il filtro posta** indesiderata (ovvero che tutti i messaggi ricevuti all'interno di questo intervallo di indirizzi IP sono impostato su "non posta indesiderata" e nessun filtro aggiuntivo viene eseguito dal servizio). Tuttavia, se uno qualsiasi di questi indirizzi IP è presente in uno degli elenchi di blocco di proprietà di Microsoft o in uno qualsiasi degli elenchi di blocco di terze parti, questi messaggi verranno comunque bloccati. È pertanto consigliabile utilizzare l'intervallo di indirizzi IP da/24 a/32. 
  
Per creare la regola del flusso di posta, eseguire la procedura seguente.
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.
    
3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.
    
4. In **Applica la regola se**, selezionare **Il mittente**, quindi scegliere **L'indirizzo IP è in tutti gli intervalli o corrisponde esattamente**.
    
5. In **specificare gli indirizzi IP**, specificare l'intervallo di indirizzi IP, fare clic su](media/ITPro-EAC-AddIcon.gif) **Aggiungi** ![icona, quindi fare clic su **OK**.
    
6. Nella casella **Effettuare le seguenti operazioni**, impostare l'azione scegliendo **Modificare le proprietà dei messaggi**, quindi **imposta il livello di probabilità di posta indesiderata (SCL)**. Nella casella **specifica SCL**, selezionare **Ignora il filtro di protezione da posta indesiderata**, quindi fare clic su **ok**.
    
7. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. [Procedure per le regole del flusso di posta in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) sono disponibili ulteriori informazioni su queste selezioni. 
    
8. Fare clic su **Salva** per salvare la regola. La regola viene visualizzata nell'elenco delle regole. 
    
Dopo aver creato e applicato la regola, il servizio ignora il filtro di posta indesiderata per l'intervallo di indirizzi IP specificato.
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Ambito delle eccezioni dell'elenco di indirizzi IP consentiti per un dominio specifico

In generale, si consiglia di aggiungere gli indirizzi IP (o gli intervalli di indirizzi IP) per tutti i domini che si considerano sicuri per l'elenco IP conSentiti. Tuttavia, se non si desidera che la voce dell'elenco indirizzi IP conSentiti sia applicabile a tutti i domini, è possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che esclude domini specifici. 
  
Ad esempio, si supponga di disporre di tre domini: ContosoA.com, ContosoB.com e ContosoC.com e si desidera aggiungere l'indirizzo IP (per motivi di semplicità, utilizzare 1.2.3.4) e ignorare il filtro solo per ContosoB.com di dominio. È necessario creare un elenco indirizzi IP conSentiti per 1.2.3.4, che imposta il livello di probabilità di posta indesiderata (SCL) su-1 (il che significa che è classificato come non indesiderato) per tutti i domini. È quindi possibile creare una regola del flusso di posta che imposta il livello SCL per tutti i domini ad eccezione di ContosoB.com su 0. In questo modo il messaggio viene rianalizzato per tutti i domini associati all'indirizzo IP, ad eccezione di ContosoB.com, che è il dominio elencato come eccezione nella regola. ContosoB.com ha ancora un SCL di-1, il che significa che il filtro è saltato, mentre ContosoA.com e ContosoC.com dispongono di SCLs pari a 0, il che significa che verranno analizzati dal filtro contenuto.
  
A tale scopo, eseguire la procedura seguente:
  
1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.
    
3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.
    
4. In **Applica la regola se**, selezionare **Il mittente**, quindi scegliere **L'indirizzo IP è in tutti gli intervalli o corrisponde esattamente**.
    
5. Nella casella **specificare gli indirizzi** IP specificare l'indirizzo IP o l'intervallo di indirizzi IP immesso nell'elenco IP consentiti, fare clic](media/ITPro-EAC-AddIcon.gif)su **Aggiungi** ![icona e quindi fare clic su **OK**.
    
6. In **Effettuare le seguenti operazioni**, impostare l'azione scegliendo **Modificare le proprietà dei messaggi**, quindi **imposta il livello di probabilità di posta indesiderata (SCL)**. Nella casella **specifica SCL**, selezionare **0**, quindi fare clic su **ok**.
    
7. Fare clic su **aggiungi eccezione** e in **Tranne se**, selezionare **Il mittente** e scegliere **il dominio è**. 
    
8. Nella casella **specificare** il dominio, immettere il dominio per il quale si desidera ignorare il filtro di posta indesiderata, ad esempio **contosob.com**. Fare **** ![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona per spostarlo nell'elenco delle frasi. Ripetere questo passaggio se si desidera aggiungere ulteriori domini come eccezioni e fare clic su **OK** al termine. 
    
9. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. [Procedure per le regole del flusso di posta in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) sono disponibili ulteriori informazioni su queste selezioni. 
    
10. Fare clic su **Salva** per salvare la regola. La regola viene visualizzata nell'elenco delle regole. 
    
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
  
[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Come assicurarsi che un messaggio non venga contrassegnato come indesiderato](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

