---
title: Configurare i criteri di posta indesiderata in uscita
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
description: Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti.
ms.openlocfilehash: b6185cfded28613cb5a512882aefb1a99db158db
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002414"
---
# <a name="configure-the-outbound-spam-policy"></a>Configurare i criteri di posta indesiderata in uscita

Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti. Come il filtro della posta in arrivo, quello per la posta indesiderata in uscita è composto da un filtro connessioni e un filtro contenuto, ma diversamente dal primo le sue impostazioni non sono configurabili. Se si determina che un messaggio in uscita è posta indesiderata, tale messaggio viene instradato attraverso il pool di recapito ad alto rischio in modo da ridurre la probabilità che il normale pool IP in uscita venga aggiunto all'elenco di indirizzi bloccati. Se un utente continua a inviare posta indesiderata in uscita tramite il servizio, non potrà più inviare messaggi. Anche se il filtro di protezione da posta indesiderata in uscita non può essere disabilitato o modificato, è possibile configurare diverse impostazioni di posta indesiderata in uscita a livello dell'azienda tramite il criterio della posta indesiderata in uscita predefinito. 
  
Nel video seguente viene illustrato come configurare il criterio della posta indesiderata in uscita:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 5 minuti
  
È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per visualizzare le autorizzazioni necessarie, vedere "protezione da posta indesiderata nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) . 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
  
La procedura seguente può anche essere eseguita tramite remote PowerShell. Utilizzare il cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) per controllare le impostazioni e [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) per modificare le impostazioni di criteri di posta indesiderata in uscita. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a>Utilizzo di EAC per modificare il criterio della posta indesiderata in uscita predefinito
<a name="sectionSection1"> </a>

Utilizzare la procedura seguente per modificare il criterio della posta indesiderata in uscita predefinito:
  
### <a name="to-configure-the-default-outbound-spam-policy"></a>Per configurare il criterio della posta indesiderata in uscita predefinito

1. Nell'interfaccia di amministrazione di Exchange (EAC), accedere a **Protezione**\> **Posta indesiderata in uscita** e fare doppio clic sul criterio predefinito.
    
2. Selezionare l'opzione di menu **Preferenze posta indesiderata in uscita**. 
    
3. Selezionare le seguenti caselle di controllo appartenenti ai messaggi in uscita e specificare l'indirizzo o gli indirizzi di posta elettronica associati nella casella di input correlata (che possono essere liste di distribuzione se risolvono come destinazioni SMTP valide):
    
1. **Inviare una copia dei messaggi di posta elettronica in uscita sospetti ai seguenti indirizzi di posta elettronica**. Questi sono messaggi contrassegnati come posta indesiderata dal filtro (a prescindere dal livello di sicurezza della protezione contro la posta indesiderata). Non vengono rifiutati dal filtro ma instradati tramite il pool di recapito ad alto rischio. Separare più indirizzi con un carattere di due punti (:). Tenere presente che i destinatari specificati riceveranno i messaggi con l'indirizzo nel campo della copia per conoscenza nascosta (Ccn), mentre i campi Da e A contengono il destinatario e il mittente originale.
    
2. **Inviare una notifica al seguente indirizzo di posta elettronica quando a un mittente viene impedito l'invio di posta indesiderata**. Separare più indirizzi con un carattere di due punti (:).
    
    Quando una grande quantità di posta indesiderata viene creato da un determinato utente, l'utente è disabilitato di inviare messaggi di posta elettronica. L'amministratore di dominio, che viene specificato l'utilizzo di questa impostazione, informa l'utente che vengono bloccati i messaggi in uscita per l'utente. Per visualizzare l'aspetto di questa notifica, vedere [esempio notifica quando un mittente viene bloccato l'invio di posta indesiderata in uscita](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Per informazioni sulla Guida riabilitata, vedere [rimozione di un utente, un dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta elettronica da posta indesiderata](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).
    
4. Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri predefiniti.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection2"> </a>

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)
  
[Domande frequenti sulla protezione anti-spam](anti-spam-protection-faq.md)
  

