---
title: Installazione del servizio EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: In questo argomento viene illustrato come configurare Microsoft Exchange Online Protection (EOP). Se si è arrivati qui dalla configurazione guidata dei domini di Office 365, tornare alla configurazione guidata dei domini di Office 365 se non si desidera utilizzare Exchange Online Protection. Per ulteriori informazioni su come configurare i connettori, vedere Configure mail flow using connectors in Office 365.
ms.openlocfilehash: 496a249f1dc269151dad4b93d2b5cf30fa6ec91b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256594"
---
# <a name="set-up-your-eop-service"></a>Configurare il servizio Exchange Online Protection

In questo argomento viene illustrato come configurare Microsoft Exchange Online Protection (EOP). Se si è arrivati qui dalla configurazione guidata dei domini di Office 365, tornare alla configurazione guidata dei domini di Office 365 se non si desidera utilizzare Exchange Online Protection. Per ulteriori informazioni su come configurare i connettori, vedere [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx).
  
> [!NOTE]
> Si presume che si disponga di cassette postali locali e che si desideri proteggerle con EOP. Questo tipo di scenario è definito autonomo. Per ospitare tutte le cassette postali nel cloud con Exchange Online, non è necessario completare tutti i passaggi di questo argomento. Andare a [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) per iscriversi e acquistare le cassette postali cloud. Uno scenario in cui alcune cassette postali vengono ospitate in locale e alcune nel cloud viene definito ibrido. Questo tipo di scenario richiede impostazioni di flusso di posta più avanzate. In [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx) viene illustrato il flusso di posta ibrido e vengono forniti i collegamenti alle risorse che mostrano come installarlo. 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 1 ora
    
- Per configurare i connettori, l'account deve essere un amministratore globale di Office 365 o un amministratore aziendale di Exchange (gruppo dei ruoli di gestione dell'organizzazione). Per ulteriori informazioni su come le autorizzazioni di Office 365 sono correlate a quelle di Exchange, vedere l'articolo relativo alle [autorizzazioni in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=335814).
    
- Se non si è iscritti a EOP, visitare [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) e scegliere di acquistare o provare il servizio. 
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>Come eseguire l'operazione?

### <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: utilizzare l'interfaccia di amministrazione di Microsoft 365 per aggiungere e verificare il dominio

1. Nell'interfaccia di amministrazione di Microsoft 365, passare a **installazione** per aggiungere il dominio al servizio. 
    
    Non si è sicuri di dove trovare l'interfaccia di amministrazione di Microsoft 365? Per ulteriori informazioni, vedere [about the Microsoft 365 Admin Center](https://go.microsoft.com/fwlink/p/?LinkId=521888).
    
2. Seguire la procedura di aggiunta dei record DNS applicabili al provider che ospita i DNS per verificare la proprietà del dominio.
    
> [!TIP]
> [Aggiungere il proprio dominio a Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) e [Creare record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166) sono risorse utili a cui fare riferimento per aggiungere il dominio al servizio e configurare DNS. 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Passaggio 2: aggiunta di destinatari e abilitazione DBEB (scelta facoltativa)

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare i connettori nell'Interfaccia di amministrazione di Exchange (EAC) per abilitare il flusso di posta tra EOP e i server di posta locali. Per istruzioni dettagliate, vedere [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx).
  
#### <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Utilizzare Analizzatore connettività remota per eseguire un test che controlla il flusso di posta tra il servizio e l'ambiente. Per ulteriori informazioni, vedere la sezione "Utilizzare l'Analizzatore connettività remota per verificare il recapito della posta elettronica" in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti dei record DNS. Successivamente, limitare il traffico SMTP della porta 25 in ingresso sul firewall o sui server di posta in modo da accettare solo la posta proveniente da datacenter EOP, specificamente dagli indirizzi IP elencati in [Indirizzi IP di EOP (Exchange Online Protection)](exchange-online-protection-ip-addresses.md). In tal modo si protegge l'ambiente locale limitando l'ambito dei messaggi in arrivo che è possibile ricevere. Inoltre, se sul server di posta sono state definite impostazioni per il controllo degli indirizzi IP a cui è consentita la connessione per l'inoltro della posta, è necessario aggiornare anche tali impostazioni.
  
> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile nella maggior parte delle situazioni perché consente un certo ritardo, ad esempio in caso di messaggi inviati con allegati di grandi dimensioni. 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: Utilizzare Shell per garantire che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente

Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. I passaggi vengono forniti in [modo che la posta indesiderata venga instradata alla cartella posta indesiderata di ogni utente](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).
  
Se non si intende spostare i messaggi nella cartella posta indesiderata di ciascun utente, è possibile optare per un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](../configure-your-spam-filter-policies.md).
  
### <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: utilizzare l'interfaccia di amministrazione di Microsoft 365 per puntare il record MX a EOP

Seguire i passaggi di configurazione del dominio di Office 365 per aggiornare il record MX relativo al proprio dominio. In questo modo, la posta elettronica in ingresso attraversa EOP. Assicurarsi di puntare il record MX direttamente verso EOP, invece di consentire a un servizio di filtro di terze parti di inoltrare la posta elettronica in EOP. Per ulteriori informazioni, fare di nuovo riferimento a [Creare record DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).
  
#### <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Utilizzare l'Analizzatore connettività remota per eseguire un test che verifica il record MX. Per ulteriori informazioni, vedere la sezione "Utilizzare l'Analizzatore connettività remota per verificare il record MX e un connettore in uscita" in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx). 
  
A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:
  
- Nell'Analizzatore connettività remota, fare clic sulla scheda **Office 365**, quindi eseguire il test **Test posta elettronica SMTP** situato sotto **Test per posta elettronica Internet**. 
    
- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,
    
- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.
    
> [!TIP]
> Al termine dell'installazione, non è necessario eseguire ulteriori operazioni perché EOP rimuova posta indesiderata e malware. EOP li rimuove automaticamente. Tuttavia, è possibile utilizzare EAC per ottimizzare le impostazioni in base ai requisiti aziendali. Per ulteriori informazioni, vedere [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx). > Quando il servizio è in esecuzione, si consiglia di leggere [Procedure consigliate per la configurazione di EOP](best-practices-for-configuring-eop.md), in cui vengono descritte le impostazioni consigliate e considerazioni per i passaggi successivi all'installazione di EOP. 
  

