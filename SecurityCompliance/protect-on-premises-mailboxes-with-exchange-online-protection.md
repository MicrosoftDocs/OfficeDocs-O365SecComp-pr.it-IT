---
title: Proteggere le cassette postali locale con Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: Anche se si prevede di ospitare alcune o tutte le cassette postali locale, è comunque possibile proteggere le cassette postali a Exchange Online Protection (EOP). Per configurare i connettori, l'account deve essere un amministratore globale di Office 365 o un Exchange Company Administrator (il gruppo di ruoli Gestione organizzazione). Per informazioni sulla correlazione tra le autorizzazioni di Office 365 per le autorizzazioni di Exchange, vedere assegnazione di ruoli di amministratore in Office 365 gestito dal 21Vianet. Se tutte le cassette postali di Exchange locale, attenersi alla procedura seguente per configurare il servizio EOP.
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531451"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Proteggere le cassette postali locale con Exchange Online Protection

> [!NOTE]
> In questo articolo si applica solo a Office 365 gestito dal 21Vianet in Cina. 
  
Anche se si prevede di ospitare alcune o tutte le cassette postali locale, è comunque possibile proteggere le cassette postali a Exchange Online Protection (EOP). Per configurare i connettori, l'account deve essere un amministratore globale di Office 365 o un Exchange Company Administrator (il gruppo di ruoli Gestione organizzazione). Per informazioni sulla correlazione tra le autorizzazioni di Office 365 per le autorizzazioni di Exchange, vedere [assegnazione di ruoli di amministratore in Office 365 gestito dal 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). Se tutte le cassette postali di Exchange locale, attenersi alla procedura seguente per configurare il servizio EOP. 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: Aggiunta e verifica del dominio tramite l'interfaccia di amministrazione di Office 365

1. Nell'interfaccia di amministrazione di Office 365, andare a Installazione per aggiungere il dominio al servizio.
    
2.  Seguire i passaggi del portale per aggiungere i record DNS applicabili al provider di hosting DNS per verificare la proprietà del dominio. 
    
> [!TIP]
> [Aggiungere il dominio e agli utenti di Office 365 gestito dal 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) e [creare record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) sono risorse utili per fare riferimento come aggiungere il dominio al servizio e configurare il DNS. 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Passaggio 2: Aggiungere destinatari e configurare il tipo di dominio

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare connettori nell'interfaccia di amministrazione di Exchange (EAC) che consentono il flusso della posta tra EOP e i server di posta locale. Per istruzioni dettagliate, vedere [Create necessarie connettori per impostare il flusso di posta elettronica base attraverso EOP](https://go.microsoft.com/fwlink/?LinkId=506780).
  
 Come verificare se l'operazione ha avuto esito positivo 
  
 Utilizzare l'analizzatore connettività remota per eseguire un test che consente di controllare il flusso della posta tra l'ambiente e il servizio. Per ulteriori informazioni, vedere la sezione "Utilizzare analizzatore connettività remota per verificare il recapito di posta elettronica" nel [flusso di posta con analizzatore connettività remota di testing](https://go.microsoft.com/fwlink/?LinkId=506784).
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti di record DNS. In seguito, limitare il traffico in ingresso SMTP porta 25 sui server firewall o di posta elettronica di accettare messaggi solo da datacenter EOP, in particolare di indirizzi IP elencati in [URL e indirizzi IP per Office 365 gestito dal 21Vianet intervalli](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). Consente di proteggere l'ambiente locale per limitare l'ambito della è possibile ricevere i messaggi in ingresso. Inoltre, se si dispone di impostazioni del server di posta elettronica che controllano gli indirizzi IP consentiti per la connessione per l'inoltro della posta, aggiornare anche le impostazioni.
  
> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile nella maggior parte delle situazioni perché consente un certo ritardo, ad esempio in caso di messaggi inviati con allegati di grandi dimensioni. 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: Utilizzare Shell per garantire che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente

Per garantire che la posta elettronica da posta indesiderata (indesiderata) sia instradata correttamente alla cartella posta indesiderata di ogni utente, è necessario eseguire due passaggi di configurazione. Vengono forniti i passaggi di [verificare che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente](https://go.microsoft.com/fwlink/?LinkId=506804). Se non si desidera spostare messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805). 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: Utilizzo dell'interfaccia di amministrazione di Office 365 per puntare il record MX a EOP

Seguire i passaggi di configurazione di dominio di Office 365 per aggiornare il record MX per il dominio in modo che la posta elettronica in ingresso passa attraverso EOP. Per ulteriori informazioni, è possibile fare riferimento nuovamente a [creare record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).
  
Come verificare se l'operazione ha avuto esito positivo
  
 Utilizzare l'analizzatore connettività remota per eseguire un test di verifica del record MX. Per ulteriori informazioni, vedere la sezione "Utilizzare analizzatore connettività remota per verificare il record MX e il connettore in uscita" nel [flusso di posta con analizzatore connettività remota di testing](https://go.microsoft.com/fwlink/?LinkId=506784). 
  
A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:
  
- Nell'Analizzatore connettività remota, fare clic sulla scheda **Office 365**, quindi eseguire il test **Test posta elettronica SMTP** situato sotto **Test per posta elettronica Internet**.
    
- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,
    
- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Meno comuni: una configurazione ibrida con le cassette postali in locale e nel cloud

Se si dispongono di Exchange in locale e uno o più cassette postali nel cloud con Exchange Online, si dispone di una configurazione *ibrida* . In una configurazione ibrida, caratteristiche, ad esempio disponibilità condivisione del calendario e il routing della posta è possibile utilizzare contemporaneamente in locale e del cloud ambienti. Potrebbe essere una configurazione ibrida in locale mentre si effettuare la transizione delle cassette postali a Exchange Online. Un ambiente ibrido è configurato in modo diverso rispetto a protezione autonomo EOP. 
  
È possibile scegliere uno scenario ibrido per sfruttare i vantaggi di posta elettronica basata sul cloud per la maggior parte dei dipendenti. È possibile eseguire questa operazione anche hosting alcune cassette postali locale; ad esempio, per il proprio ufficio legale. 
  
Una configurazione ibrida può essere complessa, ma presenta numerosi vantaggi. Per ulteriori informazioni su come configurare gli scenari ibridi con Exchange, vedere [funzionalità di distribuzione ibrida di configurazione di Exchange con Office 365 gestito dal 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).
  

