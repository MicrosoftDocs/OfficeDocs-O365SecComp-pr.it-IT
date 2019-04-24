---
title: Impostare i criteri di anti-phishing ATP di Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: La protezione anti-phishing, con una protezione globale come parte di Office 365 Advanced Threat Protection e la protezione di base in Office 365 Exchange Online Protection, può contribuire a proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri attacchi di phishing.
ms.openlocfilehash: 4a647463dd37261cfa1f4c2fd2901ed8f12902b7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266965"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a>Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP 

La [protezione anti-phishing ATP](atp-anti-phishing.md), parte di [Office 365 Advanced Threat Protection](office-365-atp.md), può aiutare a proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri attacchi di phishing. Se si è un amministratore globale o di sicurezza di Office 365 Enterprise, è possibile configurare i criteri di anti-phishing ATP. 

Gli attacchi di phishing sono disponibili in una varietà di forme di attacchi basati su prodotti a base di phishing o di caccia alle balene mirate. Con la crescente complessità, è difficile anche per un occhio addestrato per identificare alcuni di questi attacchi sofisticati. Fortunatamente, Office 365 Advanced Threat Protection può essere di aiuto. È possibile configurare un criterio di anti-phishing ATP per garantire che l'organizzazione sia protetta da tali attacchi.
  
> [!NOTE]
> L'anti-phishing ATP è disponibile solo in Advanced Threat Protection (ATP). ATP è incluso nelle sottoscrizioni, ad esempio [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education a5 e così via. Se nell'organizzazione è presente un abbonamento a Office 365 che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Verificare che l'organizzazione utilizzi la versione più recente di Office 365 ProPlus su Windows per sfruttare al meglio la protezione anti-phishing ATP. 

È inoltre disponibile un criterio anti-phishing per Office 365 Exchange Online Protection, con un insieme limitato di protezione anti-spoofing che è destinato a proteggere gli attacchi basati sull'autenticazione e sull'inganno.
  
cosa fare:
  
1. Esaminare i prerequisiti.
    
2. Informazioni sulle opzioni per il criterio anti-phishing e anti-phishing ATP.
    
3. Configurare un criterio anti-phishing o un criterio di anti-phishing ATP.
    
## <a name="review-the-prerequisites"></a>Esaminare i prerequisiti

- Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente: <br>

    |Ruolo  |Dove/come assegnato  |
    |---------|---------|
    |Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
    |Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
    |Gestione dell'organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
    Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- È probabile che vengano configurati più criteri di anti-phishing per l'organizzazione. Office 365 applica questi criteri nell'ordine in cui sono elencati nella **pagina anti-phishing** e nelle pagine antiphishing **ATP** nel centro sicurezza &amp; e conformità. Dopo aver esaminato le [Opzioni relative ai criteri](#learn-about-atp-anti-phishing-policy-options), prendere un po' di tempo per determinare il numero di criteri necessari e la priorità per ognuno di essi. 
    
- Pianificare di spendere circa 5-15 minuti per impostare il primo criterio anti-phishing.
    
- Consentono fino a 30 minuti affinché il criterio nuovo o aggiornato venga esteso a tutti i datacenter di Office 365.
    
## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Configurare un anti-phishing o un criterio anti-phishing ATP

Ogni organizzazione in Office 365 ha un criterio di anti-phishing predefinito che si applica a tutti gli utenti. È possibile creare più criteri di anti-phishing personalizzati che è possibile applicare a utenti, gruppi o domini specifici all'interno dell'organizzazione. I criteri personalizzati creati hanno la precedenza sul criterio predefinito. È possibile aggiungere, modificare ed eliminare i criteri anti-phishing nel centro sicurezza &amp; e conformità di Office 365.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione. 
    
2. Nel riquadro di spostamento a &amp; sinistra del Centro sicurezza e conformità di Office 365 fare clic su **criteri**in **gestione minacce**.
    
3. Nella pagina **criterio** scegliere **anti-phishing** o **anti-phishing ATP**.
    
4. Nella pagina anti **-phishing** o **anti-phishing ATP** eseguire una delle operazioni seguenti: 
    
    - Per aggiungere un nuovo criterio selezionare **+ Crea**.
    - Per modificare un criterio esistente, selezionare il nome del criterio nell'elenco visualizzato nella pagina **anti-phishing** . In alternativa, è possibile o scegliere il **criterio predefinito** sopra l'elenco. Nella pagina visualizzata fare clic su **modifica criterio**.  
    
5. Specificare il nome, la descrizione e le impostazioni per il criterio. Per ulteriori informazioni, vedere informazioni [sulle opzioni relative ai criteri di anti-phishing ATP](#learn-about-atp-anti-phishing-policy-options) . 
    
6. Dopo aver esaminato le impostazioni, scegliere **crea questo criterio** (o **Salva**). 
    
## <a name="learn-about-atp-anti-phishing-policy-options"></a>Informazioni sulle opzioni per i criteri di anti-phishing ATP

Quando si configurano o si modificano i criteri di anti-phishing ATP, è possibile scegliere tra diverse opzioni che offrono la protezione più sofisticata e completa, come descritto nella tabella seguente:
  
|**Questa impostazione**|**Produce questo risultato**|**Utilizzare se si desidera eseguire le operazioni seguenti:**|
|:-----|:-----|:-----|
|**Aggiungere gli utenti a Protect** <br/> |Definisce quali indirizzi di posta elettronica verranno protetti dal criterio. È possibile aggiungere fino a 60 indirizzi interni ed esterni che si desidera proteggere dalla rappresentazione.  <br/> |Quando si desidera garantire che la posta esterna all'organizzazione non sia una rappresentazione di uno degli utenti nell'elenco degli utenti da proteggere. Esempi di utenti che si desidera proteggere sono dirigenti di alto livello, proprietari di aziende, membri del Consiglio di amministrazione esterni e così via.  <br/> Questo elenco di utenti protetti è diverso dall'elenco delle persone a cui si applica il criterio, o meglio, per cui viene applicato il criterio. È possibile definire l'elenco si applica a nella sezione **applicato a** delle opzioni dei criteri.  <br/> Ad esempio, se si aggiunge `Mary Smith <marys@contoso.com>` come utente per la protezione, applicare il criterio al gruppo "tutti gli utenti". In questo modo, un messaggio di posta elettronica che è apparso per rappresentare "Mary Smith" inviato a un utente nel gruppo "tutti gli utenti" verrebbe agito dal criterio.  <br/> |
|**Aggiungere domini da proteggere** <br/> |Consente di scegliere i domini che si desidera proteggere dalla rappresentazione. È possibile specificare che i criteri includano tutti i domini personalizzati, un elenco separato da virgole di domini o una combinazione dei due. Se si sceglie di **includere automaticamente i domini che**possiedo e successivamente si aggiunge un dominio alla propria organizzazione di Office 365, questo criterio di anti-phishing sarà sul posto per il nuovo dominio.  <br/> |Ogni volta che si desidera garantire che la posta all'esterno dell'organizzazione non sia una rappresentazione di uno dei domini definiti nell'elenco dei domini verificati o di un dominio del partner.  <br/> |
|**Scegliere azioni** <br/> |Scegliere l'azione da intraprendere quando Office 365 rileva un tentativo di rappresentazione nei confronti degli utenti e dei domini aggiunti al criterio. È possibile scegliere diverse azioni per gli utenti e i domini nello stesso criterio anti-phishing. Queste azioni si applicano a tutti i messaggi di posta elettronica in arrivo identificati da Office 365 come rappresentanza di un account utente o di un dominio che si trova sotto la protezione di questo criterio anti-phishing.  <br/> **Messaggio** in quarantena La posta elettronica verrà inviata alla quarantena di Office 365. Quando si sceglie questa opzione, il messaggio di posta elettronica non viene inviato al destinatario originale.  <br/> **Reindirizza il messaggio a un altro indirizzo di posta elettronica** Il messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica specificato. È possibile specificare più indirizzi di posta elettronica. Quando si sceglie questa opzione, il messaggio di posta elettronica non viene inviato al destinatario originale.  <br/> **Spostare il messaggio nella cartella posta indesiderata dei destinatari** La posta elettronica verrà inviata alla cartella posta inDesiderata dei destinatari. Quando si sceglie questa opzione, il messaggio di posta elettronica viene comunque inviato al destinatario originale ma non viene inserito nella cartella posta in arrivo del destinatario.  <br/> **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn** Il messaggio di posta elettronica verrà recapitato al destinatario originale. Inoltre, gli utenti identificati verranno aggiunti alla riga Ccn del messaggio prima che vengano recapitati. Quando si sceglie questa opzione, il messaggio di posta elettronica viene comunque inviato alla cartella posta in arrivo del destinatario originale.  <br/> **Non applicare alcuna azione** Il messaggio di posta elettronica verrà recapitato nella cartella posta in arrivo del destinatario originale. Nessun'altra azione verrà eseguita sul messaggio di posta elettronica.  <br/> **Attiva suggerimenti per la protezione del phishing** Consente di abilitare i suggerimenti per la sicurezza anti-phishing nella posta elettronica.  <br/> |Quando si desidera eseguire un'azione sui messaggi che Office 365 ha determinato come rappresentazione di un utente o di un dominio come definito nel criterio.  <br/> |
|**Abilitazione dell'Intelligence delle cassette postali** <br/> |Abilita o Disabilita l'intelligence delle cassette postali per questo criterio. È possibile abilitare l'intelligence delle cassette postali solo per gli account basati su cloud, ovvero gli account la cui cassetta postale è ospitata interamente in Office 365.  <br/> |Quando si desidera migliorare i risultati della rappresentazione per gli utenti in base alla mappa del mittente individuale di ogni utente. L'intelligence delle cassette postali è sviluppata attorno alle persone a cui invii e ricevi la posta. Questa funzionalità di Intelligence consente a Office 365 di personalizzare i criteri di rappresentazione a livello di utente per gestire al meglio i risultati dei falsi positivi.  <br/> |
|**Aggiungere mittenti e domini attendibili** <br/> |Definisce gli indirizzi di posta elettronica e i domini che non verranno considerati come rappresentati da questo criterio. I messaggi provenienti da indirizzi e domini di posta elettronica del mittente che si aggiungono come mittenti e domini attendibili non verranno mai classificati come attacchi basati sulla rappresentazione. Di conseguenza, le azioni e le impostazioni di questo criterio non verranno applicate ai messaggi provenienti da questi mittenti e domini.  <br/> |Quando gli utenti interagiscono con i domini o gli utenti che attivano la rappresentazione ma sono considerati sicuri. Ad esempio, se un partner ha lo stesso nome di visualizzazione o nome di dominio simile a un utente definito nell'elenco.  <br/> |
|**Applicato a** <br/> |Definisce i destinatari i cui messaggi di posta elettronica in arrivo saranno soggetti alle regole del criterio. È possibile creare condizioni ed eccezioni per i destinatari associati al criterio.  <br/> Ad esempio, è possibile creare un criterio globale per l'organizzazione applicando la regola a tutti i destinatari del dominio.  <br/> È inoltre possibile creare regole di eccezione, ad esempio una regola che non esegue l'analisi dei messaggi di posta elettronica per un gruppo specifico di destinatari.  <br/> |Ogni criterio deve essere associato a un gruppo di utenti, ad esempio, gli utenti di un determinato dominio.  <br/> |
|**Soglie di phishing avanzate** <br/> |Definisce il livello di impostazioni per la gestione dei messaggi di phishing.  <br/> **Standard** La posta elettronica sospettata di essere phishing viene gestita nel modo standard.  <br/> **** In modo aggressivo La posta elettronica sospettata di essere phishing con un livello elevato o molto elevato di sicurezza è gestita dal sistema nello stesso modo.  <br/> **Più aggressivo** La posta elettronica sospettata di essere phishing con un livello di confidenza medio, alto o molto elevato viene gestita dal sistema nello stesso modo.  <br/> **Più aggressivo** La posta elettronica sospettata di essere phishing con un livello di confidenza basso, medio, alto o molto elevato viene gestita dal sistema nello stesso modo.  <br/> |Quando si vuole essere più aggressivi nel trattamento di messaggi potenzialmente di phishing all'interno di Office 365. Ad esempio, i messaggi con un'altissima probabilità di essere phishing avranno le azioni più aggressive intraprese su di esse, mentre i messaggi con una probabilità bassa sono state intraprese azioni meno aggressive. Questa impostazione incide anche su altre parti del sistema di filtraggio che combinano i segnali insieme. La possibilità di spostare i messaggi positivi aumenta man mano che aumenta il livello di impostazioni.  <br/>|
   
## <a name="learn-about-anti-phishing-policy-options"></a>Informazioni sulle opzioni dei criteri di anti-phishing 

Durante la configurazione o la modifica dell'anti-phishing, è possibile scegliere tra diverse opzioni, come descritto nella tabella seguente: 

|**Questa impostazione**|**Produce questo risultato**|**Utilizzare se si desidera eseguire le operazioni seguenti:**|
|:-----|:-----|:-----|
|**Applicato a** <br/> |Definisce i destinatari i cui messaggi di posta elettronica in arrivo saranno soggetti alle regole del criterio. È possibile creare condizioni ed eccezioni per i destinatari associati al criterio.  <br/> Ad esempio, è possibile creare un criterio globale per l'organizzazione applicando la regola a tutti i destinatari del dominio.  <br/> È inoltre possibile creare regole di eccezione, ad esempio una regola che non esegue l'analisi dei messaggi di posta elettronica per un gruppo specifico di destinatari.  <br/> |Ogni criterio deve essere associato a un gruppo di utenti, ad esempio, gli utenti di un determinato dominio.  <br/> | 
|**Scegliere azioni** <br/> |Scegliere l'azione da intraprendere quando Office 365 rileva un tentativo di spoofing tra org o External-org nei confronti degli utenti. Queste azioni si applicano a tutti i messaggi di posta elettronica in arrivo identificati da Office 365 come tentativo di spoofing per gli utenti che si trovano sotto la protezione di questo criterio anti-phishing.  <br/> **Messaggio** in quarantena La posta elettronica verrà inviata alla quarantena di Office 365. Quando si sceglie questa opzione, il messaggio di posta elettronica non viene inviato al destinatario originale.  <br/> **Spostare il messaggio nella cartella posta indesiderata dei destinatari** La posta elettronica verrà inviata alla cartella posta inDesiderata dei destinatari. Quando si sceglie questa opzione, il messaggio di posta elettronica viene comunque inviato al destinatario originale ma non viene inserito nella cartella posta in arrivo del destinatario.  <br/> **Non applicare alcuna azione** Il messaggio di posta elettronica verrà recapitato nella cartella posta in arrivo del destinatario originale. Nessun'altra azione verrà eseguita sul messaggio di posta elettronica.  <br/> |Quando si desidera eseguire un'azione sui messaggi che Office 365 ha determinato come tentativo di spoofing dei domini interni o esterni, come definito nel criterio.  <br/>|

Dopo che l'organizzazione ha configurato Criteri di anti-phishing o criteri di anti-phishing ATP, è possibile vedere come funziona il servizio [visualizzando i report per Advanced Threat Protection](view-reports-for-atp.md).
  
## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Esempio: criteri di anti-phishing per la protezione di un utente e di un dominio

In questo esempio viene impostato un criterio denominato "Domain and CEO" che fornisce la protezione sia degli utenti che dei domini dalla rappresentazione e quindi applica il criterio a tutti i messaggi di posta elettronica `contoso.com`ricevuti dagli utenti all'interno del dominio. L'amministratore della sicurezza ha stabilito che il criterio deve soddisfare i requisiti aziendali seguenti:
  
- Il criterio deve fornire protezione per l'account di posta elettronica del CEO e l'intero dominio.
    
- I messaggi che vengono determinati come tentativi di rappresentazione per l'account utente del CEO devono essere reindirizzati all'indirizzo di posta elettronica dell'amministratore della sicurezza.
    
- I messaggi che vengono determinati come tentativi di rappresentazione nel dominio sono meno urgenti e devono essere messi in quarantena per la revisione successiva.
    
L'amministratore della sicurezza di Contoso può utilizzare valori analoghi al seguente per creare un criterio di anti-phishing che soddisfi queste esigenze.
  
|||
|:-----|:-----|
|**Impostazione o opzione** <br/> |**Esempio** <br/> |
|Name  <br/> |Dominio e CEO  <br/> |
|Descrizione  <br/> |Verificare che il CEO e il dominio non vengano rappresentati.  <br/> |
|Aggiungere gli utenti a Protect  <br/> |L'indirizzo di posta elettronica del CEO come minimo.  <br/> |
|Aggiungere domini da proteggere  <br/> |Il dominio dell'organizzazione che include l'ufficio del CEO.  <br/> |
|Scegliere azioni  <br/> |Se la posta elettronica viene inviata da un utente rappresentato: scegliere **reindirizza messaggio a un altro indirizzo di posta elettronica** e quindi digitare l'indirizzo di posta elettronica dell'amministratore `securityadmin@contoso.com`della protezione, ad esempio.  <br/> Se il messaggio di posta elettronica viene inviato da un dominio rappresentato: scegliere **Quarantine Message**.  <br/> |
|Intelligence delle cassette postali  <br/> |Per impostazione predefinita, la funzionalità di intelligence delle cassette postali viene selezionata quando si crea un nuovo criterio anti-phishing. Lasciare questa impostazione **** per ottenere risultati ottimali.  <br/> |
|Aggiungere mittenti e domini attendibili  <br/> |In questo esempio non vengono definite eventuali sostituzioni.  <br/> |
|Applicato a  <br/> |Selezionare **il dominio del destinatario**. In **uno di questi**, seleziona **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome del dominio, ad esempio `contoso.com`, nell'elenco e quindi selezionare **Aggiungi**. Scegliere **Fine**.  <br/> |
   
## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Eliminare un anti-phishing o un criterio anti-phishing ATP

È possibile eliminare i criteri personalizzati creati utilizzando il Centro sicurezza &amp; e conformità. Non è possibile eliminare il criterio predefinito per l'organizzazione. È consigliabile utilizzare il centro &amp; sicurezza e conformità per esaminare o modificare i criteri ATP.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione. 
    
2. Nella barra di spostamento sinistra fare clic su **criteri**in **gestione minacce**.
    
3. Nella pagina **criterio** scegliere **anti-phishing** o **anti-phishing ATP**.
    
4. Nella pagina anti- **phishing** o **anti-phishing ATP** Selezionare il nome del criterio nell'elenco.

5. Nella pagina che viene visualizzata, scegliere **Delete Policy**. Consentono fino a 30 minuti affinché le modifiche vengano estese a tutti i datacenter di Office 365.
    

## <a name="next-steps"></a>Passaggi successivi

Una volta attivati i criteri di anti-phishing, è possibile vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report. Per ulteriori informazioni, vedere le risorse seguenti:
- [Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md) o [visualizzare i report sulla sicurezza della posta elettronica](view-email-security-reports.md)
- [Utilizzo di Esplora risorse (noto anche come Esplora minacce)](use-explorer-in-security-and-compliance.md)

Rimanere in cima a nuove funzionalità che vengono a ATP. visitare la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e conoscere le [nuove funzionalità che vengono aggiunte a ATP](office-365-atp.md#new-features-in-office-365-atp).
 