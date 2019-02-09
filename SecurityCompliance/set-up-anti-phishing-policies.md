---
title: Configurare i criteri anti-phishing ATP di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
description: Protezione anti-phishing, con una protezione globale come parte di Office 365 avanzate rischio protezione e protezione di base in Office 365 Exchange Online Protection consentono di proteggere l'organizzazione da attacchi dannosi phishing basato su rappresentazione e altri phishing.
ms.openlocfilehash: 333176ebef8d6367f5090730386fc820927cf3af
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792281"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a>Impostazione dei criteri anti-phishing e anti-phishing degli strumenti di analisi di Office 365

[Protezione anti-phishing degli strumenti di analisi](atp-anti-phishing.md), parte di [Protezione di Office 365 avanzate rischio](office-365-atp.md), consentono di proteggere l'organizzazione da attacchi dannosi phishing basato su rappresentazione e altri attacchi di phishing. Se si è un amministratore di protezione o di Office 365 modello globale dell'organizzazione, è possibile impostare i criteri di anti-phishing degli strumenti di analisi. 

Il phishing di attacchi in una vasta gamma di moduli di attacchi basati su merce destinazione spear phishing o whaling. Con la complessità crescente è difficile per anche una formazione occhio identificare alcuni di questi attacchi sofisticati. Fortunatamente, può contribuire a Office 365 avanzate Threat Protection. È possibile impostare i criteri di anti-phishing degli strumenti di analisi per contribuire a garantire che l'organizzazione è protetto contro gli attacchi descritti.
  
> [!NOTE]
> Protezione anti-phishing degli strumenti di analisi disponibile solo in avanzate Threat Protection (degli strumenti di analisi). Degli strumenti di analisi è incluso in sottoscrizioni, ad esempio [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), E5 Enterprise di Office 365, Office 365 Education A5 e così via. Se l'organizzazione dispone di una sottoscrizione a Office 365 che non include degli strumenti di analisi di Office 365, è possibile acquistare potenzialmente degli strumenti di analisi come componente aggiuntivo. Per ulteriori informazioni, vedere [i piani Office 365 avanzate Threat Protection e i prezzi](https://products.office.com/exchange/advance-threat-protection) e [Office 365 avanzate Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Verificare che l'organizzazione utilizza la versione più recente di Office 365 ProPlus su Windows per sfruttare al meglio la protezione anti-phishing degli strumenti di analisi. 

Un criterio di protezione anti-phishing è disponibile anche per Office 365 Exchange Online Protection, con un numero limitato di protezione anti-spoofing che ha lo scopo di protezione contro gli attacchi basati su descrizione e l'autenticazione.
  
cosa fare:
  
1. Verificare i prerequisiti.
    
2. Per conoscere il anti-phishing e opzioni dei criteri anti-phishing degli strumenti di analisi.
    
3. Consente di impostare un criterio di protezione anti-phishing o un criterio di protezione anti-phishing degli strumenti di analisi.
    
## <a name="review-the-prerequisites"></a>Verificare i prerequisiti

- Per definire o modificare i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito: <br>

    |Ruolo  |Modalità assegnato  |
    |---------|---------|
    |Amministratore globale di Office 365 |La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.         |
    |Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online Organization Management |Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
    Per ulteriori informazioni sui ruoli e autorizzazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).

- È probabile che verranno impostare più criteri anti-phishing per l'organizzazione. Office 365 consente di applicare questi criteri nell'ordine sono elencate nelle pagine di **Anti-phishing pagina** e **degli strumenti di analisi anti-phishing** in sicurezza &amp; centro conformità. Dopo che è stato rivisto le [Opzioni dei criteri](#learn-about-atp-anti-phishing-policy-options), richiedere tempo per determinare quanti criteri necessari e la priorità per ognuno. 
    
- Pianificare impiegato circa 5-15 minuti per configurare i criteri di anti-phishing primo.
    
- Consentire fino a 30 minuti per il criterio di nuovo o aggiornato da distribuire a tutti i centri dati di Office 365.
    
## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Impostare una protezione anti-phishing o dei criteri anti-phishing degli strumenti di analisi

Ogni organizzazione in Office 365 dispone di un criterio di protezione anti-phishing predefinito che si applica a tutti gli utenti. È possibile creare più criteri anti-phishing personalizzati che è possibile definire l'ambito a specifici utenti, gruppi o domini all'interno dell'organizzazione. I criteri personalizzati creati hanno la precedenza sul criterio predefinito. Aggiungere, modificare ed eliminare i criteri anti-phishing in Office 365 Security &amp; centro conformità.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. In Office 365 Security &amp; centro conformità, nel riquadro di spostamento a sinistra, in **gestione rischio**, scegliere **criterio**.
    
3. Nella pagina **criteri** scegliere **Anti-phishing** o **degli strumenti di analisi anti-phishing**.
    
4. Nella pagina **protezione Anti-phishing** o **degli strumenti di analisi anti-phishing** , effettuare una delle operazioni seguenti: 
    
    - Per aggiungere un nuovo criterio selezionare **Crea +**.
    - Per modificare un criterio esistente, selezionare il nome del criterio nell'elenco visualizzato nella pagina **protezione Anti-phishing** . (In alternativa, è possibile o scegliere **Criterio predefinito** sopra l'elenco.) Nella pagina visualizzata, scegliere **Modifica criterio**.  
    
5. Specificare il nome, descrizione e le impostazioni per il criterio. Per ulteriori informazioni, vedere [informazioni sulle opzioni dei criteri anti-phishing degli strumenti di analisi](#learn-about-atp-anti-phishing-policy-options) . 
    
6. Dopo aver esaminato le impostazioni, scegliere **Crea questi criteri** (o **salvare**). 
    
## <a name="learn-about-atp-anti-phishing-policy-options"></a>Informazioni sulle opzioni di criteri di anti-phishing degli strumenti di analisi

Come si consente di impostare o modificare i criteri di anti-phishing degli strumenti di analisi, è possibile scegliere tra diverse opzioni che forniscono una protezione più sofisticata e completa, come descritto nella tabella riportata di seguito:
  
|**Questa impostazione**|**Produce questo risultato**|**Utilizzare quando si desidera:**|
|:-----|:-----|:-----|
|**Aggiungere utenti per la protezione** <br/> |Definisce le quali gli indirizzi di posta elettronica saranno protetti dal criterio. È possibile aggiungere fino a 60 indirizzi interni ed esterni che si desidera impedire la rappresentazione.  <br/> |Quando si desidera verificare che la posta all'esterno dell'organizzazione non è una rappresentazione di uno degli utenti nell'elenco degli utenti che si desidera proteggere. Esempi di utenti che è possibile proteggere sono dirigenti di alto livello, titolari, esterni scheda membri e così via.<br/> In questo elenco di utenti protetti è diverso dall'elenco di utenti cui applica il criterio, oppure piuttosto, per cui viene applicato il criterio. Definire il si applica all'elenco nella sezione **applicata a** delle opzioni dei criteri.<br/> Ad esempio, se si aggiungono `Mary Smith <marys@contoso.com>` come utente per la protezione, quindi applicare i criteri per il gruppo "tutti gli utenti". In tal modo che un messaggio che veniva visualizzato per rappresentare "Mario Rossi" inviato a un utente al gruppo "Tutti gli utenti" sarebbe applicato dal criterio.<br/> |
|**Aggiunta di domini per la protezione** <br/> |Consente di scegliere i domini che si desidera impedire la rappresentazione. È possibile specificare che il criterio sono inclusi tutti i domini personalizzati, un elenco separato da virgole dei domini o una combinazione delle due configurazioni. Se si sceglie di **includere automaticamente i domini che proprietari**e in seguito si aggiunge un dominio all'organizzazione di Office 365, questi criteri anti-phishing sarà sul posto per il nuovo dominio.<br/> |Ogni volta che si desidera verificare che la posta proveniente da all'esterno dell'organizzazione non è una rappresentazione di uno dei domini definiti nell'elenco dei domini verificati o di un dominio partner.  <br/> |
|**Scegliere azioni** <br/> |Scegliere l'azione da eseguire quando Office 365 rileva un tentativo di rappresentazione per gli utenti e i domini che aggiunti al criterio. È possibile scegliere azioni diverse per gli utenti e i domini negli stessi criteri di anti-phishing. Queste operazioni si applicano a qualsiasi messaggio di posta elettronica in arrivo che è stato identificato da Office 365 come un account utente di rappresentazione o dominio con la protezione di questi criteri anti-phishing.<br/> **Messaggi in quarantena** Messaggio di posta elettronica verrà inviata alla quarantena di Office 365. Quando si sceglie questa opzione, il messaggio di posta elettronica non verrà inviato al destinatario originale.<br/> **Reindirizzare i messaggi a un altro indirizzo di posta elettronica** Messaggio di posta elettronica verrà inviato all'indirizzo specificato. È possibile specificare più indirizzi di posta elettronica. Quando si sceglie questa opzione, il messaggio di posta elettronica non verrà inviato al destinatario originale.<br/> **Spostare il messaggio nella cartella posta indesiderata per i destinatari** Messaggio di posta elettronica verrà inviato alla cartella posta indesiderata per i destinatari. Quando si sceglie questa opzione, il messaggio di posta elettronica ancora inviato al destinatario originale ma non viene inserito nella cartella Posta in arrivo del destinatario.<br/> **Recapitare il messaggio e aggiungere altri indirizzi per il campo Ccn** Messaggio di posta elettronica viene recapitato al destinatario originale. Inoltre, gli utenti che si identifica verranno aggiunto alla riga Ccn del messaggio prima del recapito. Quando si sceglie questa opzione, il messaggio di posta elettronica viene comunque inviato alla posta in arrivo del destinatario originario.<br/> **Non applica alcuna azione** Messaggio di posta elettronica devono essere recapitato posta in arrivo del destinatario originario. Verrà eseguita alcuna azione altre nel messaggio di posta elettronica.<br/> **Attivare i suggerimenti di protezione anti-phishing** Abilita suggerimenti sulla protezione anti-phishing sicurezza nel messaggio di posta elettronica.  <br/> |Se si desidera eseguire un'azione sui messaggi che Office 365 ha determinato da una rappresentazione di un utente o un dominio definito nel criterio.  <br/> |
|**Abilitare intelligence delle cassette postali** <br/> |Abilita o disabilita business intelligence della cassetta postale per questo criterio. È possibile abilitare solo intelligence cassetta postale basata sul cloud per gli account di, vale a dire, gli account di cui è in hosting interamente in Office 365.  <br/> |Se si desidera migliorare i risultati di rappresentazione per utenti in base al mapping dei singoli mittenti di ogni utente. Business intelligence della cassetta postale è basata sugli utenti di inviare e ricevere la posta. Questo intelligence consente a Office 365 personalizzare i criteri di rappresentazione a livello di utente per gestire meglio falsi positivi risultati.  <br/> |
|**Aggiungere domini e mittenti attendibili** <br/> |Definisce gli indirizzi di posta elettronica e i domini che non verranno considerati impersonations da questo criterio. I messaggi provenienti da indirizzi di posta elettronica e i domini aggiunti come mittenti attendibili e domini non verranno mai essere classificati come un attacco basato sulla rappresentazione. Di conseguenza, le azioni e le impostazioni di questo criterio non essere applicate ai messaggi da questi mittenti e domini.  <br/> |Quando gli utenti interagiscono con i domini o utenti che attivano la rappresentazione, ma sono considerati attendibili. Ad esempio, se un partner dispone stesso/simile visualizzare nome o il nome di dominio con un account utente definito nell'elenco.  <br/> |
|**Applicato a** <br/> |Definisce i destinatari il cui messaggi di posta elettronica in arrivo saranno soggette alle regole del criterio. È possibile creare condizioni ed eccezioni per i destinatari associati al criterio.  <br/> Ad esempio, è possibile creare un criterio globale per l'organizzazione applicando la regola a tutti i destinatari nel dominio.  <br/> È inoltre possibile creare le regole di eccezione, ad esempio una regola che non analizza i messaggi di posta elettronica per un gruppo di destinatari specifico.  <br/> |Ogni criterio deve essere associato a un insieme di utenti, ad esempio, gli utenti in un dominio o gruppo specifico.  <br/> |
|**Soglie phishing avanzate** <br/> |Definisce il livello delle impostazioni per la modalità di gestione dei messaggi di phishing.  <br/> **Standard** Messaggio di posta elettronica sospettata da per attività di phishing viene gestito in modo tradizionale.  <br/> **Aggressivo** Messaggio di posta elettronica sospetto a essere per attività di phishing con un'elevata o molto elevato livello di probabilità vengono gestite dal sistema nello stesso modo.  <br/> **Livello di protezione** Messaggio di posta elettronica sospetto a essere per attività di phishing con medio, alto, o molto elevato livello di probabilità vengono gestite dal sistema nello stesso modo.  <br/> **Più aggressivo** Messaggio di posta elettronica sospetto per attività di phishing con un basso, medio, elevato o molto elevato livello di probabilità di essere vengono gestite dal sistema nello stesso modo.  <br/> |Se si desidera utilizzare maggiormente trattamento dei messaggi di phishing potenzialmente in Office 365. Ad esempio, i messaggi con un elevato probabilità di essere per attività di phishing avranno le azioni più aggressive eseguite su di essi, mentre i messaggi con una probabilità bassa sono meno aggressive azioni intraprese su di essi. Questa impostazione influisce anche sulle altre parti del sistema di filtro che combinano i segnali tra loro. Aumenta la possibilità di spostamento dei messaggi di una buona il livello di aumentare le impostazioni.  <br/>|
   
## <a name="learn-about-anti-phishing-policy-options"></a>Informazioni sulle opzioni di criteri di anti-phishing 

Come si consente di impostare o modificare il protezione anti-phishing, è possibile scegliere tra diverse opzioni, come descritto nella tabella riportata di seguito: 

|**Questa impostazione**|**Produce questo risultato**|**Utilizzare quando si desidera:**|
|:-----|:-----|:-----|
|**Applicato a** <br/> |Definisce i destinatari il cui messaggi di posta elettronica in arrivo saranno soggette alle regole del criterio. È possibile creare condizioni ed eccezioni per i destinatari associati al criterio.  <br/> Ad esempio, è possibile creare un criterio globale per l'organizzazione applicando la regola a tutti i destinatari nel dominio.  <br/> È inoltre possibile creare le regole di eccezione, ad esempio una regola che non analizza i messaggi di posta elettronica per un gruppo di destinatari specifico.  <br/> |Ogni criterio deve essere associato a un insieme di utenti, ad esempio, gli utenti in un dominio o gruppo specifico.  <br/> | 
|**Scegliere azioni** <br/> |Scegliere l'azione da eseguire quando Office 365 rileva un tentativo di spoofing organizzazione all'interno o esterno org rispetto agli utenti. Queste operazioni si applicano a qualsiasi messaggio di posta elettronica in arrivo che è stato identificato da Office 365 come un tentativo di spoofing per gli utenti che sono sotto la protezione di questi criteri anti-phishing.<br/> **Messaggi in quarantena** Messaggio di posta elettronica verrà inviata alla quarantena di Office 365. Quando si sceglie questa opzione, il messaggio di posta elettronica non verrà inviato al destinatario originale.<br/> **Spostare il messaggio nella cartella posta indesiderata per i destinatari** Messaggio di posta elettronica verrà inviato alla cartella posta indesiderata per i destinatari. Quando si sceglie questa opzione, il messaggio di posta elettronica ancora inviato al destinatario originale ma non viene inserito nella cartella Posta in arrivo del destinatario.<br/> **Non applica alcuna azione** Messaggio di posta elettronica devono essere recapitato posta in arrivo del destinatario originario. Verrà eseguita alcuna azione altre nel messaggio di posta elettronica.<br/> |Se si desidera eseguire un'azione sui messaggi che ha determinato da un tentativo di spoofing dei domini interni o esterni definiti nei criteri di Office 365.  <br/>|

Dopo che l'organizzazione sono stati configurati criteri anti-phishing o ai criteri anti-phishing degli strumenti di analisi, è possibile visualizzare come il servizio sta visualizzando i [report per la protezione avanzata di rischio](view-reports-for-atp.md).
  
## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Esempio: Criteri di Anti-phishing per proteggere un utente e un dominio

Questo esempio viene configurato un criterio denominato "Dominio e CEO" assicurata da rappresentazione dell'utente e dominio e quindi viene applicato il criterio per tutta la posta elettronica ricevuta da parte di utenti all'interno del dominio `contoso.com`. L'amministratore della sicurezza ha rilevato che il criterio deve soddisfare questi requisiti aziendali:
  
- I criteri devono essere fornisce una protezione per l'amministratore delegato del dominio e account di posta elettronica.
    
- I messaggi che dipendono da tentativi di rappresentazione dell'account utente dell'amministratore delegato necessario vengano reindirizzati a indirizzo di posta elettronica dell'amministratore della protezione.
    
- I messaggi che dipendono da tentativi di rappresentazione del dominio sono meno urgenti e devono essere messi in quarantena per un utilizzo successivo.
    
L'amministratore di protezione di Contoso potrebbe utilizzare valori simile al seguente per creare un criterio di protezione anti-phishing che soddisfi le esigenze.
  
|||
|:-----|:-----|
|**Opzione o impostazione** <br/> |**Esempio** <br/> |
|Name  <br/> |Dominio e amministratore delegato  <br/> |
|Descrizione  <br/> |Verificare che il dominio e amministratore delegato non sono rappresentati.  <br/> |
|Aggiungere utenti per la protezione  <br/> |Indirizzo di posta elettronica dell'amministratore delegato minimo.  <br/> |
|Aggiunta di domini per la protezione  <br/> |Il dominio dell'organizzazione che include l'ufficio di amministratore delegato.  <br/> |
|Scegliere azioni  <br/> |Se il messaggio di posta elettronica viene inviato da un utente rappresentato: scegliere **reindirizza messaggio a un altro indirizzo di posta elettronica** e quindi digitare l'indirizzo di posta elettronica dell'amministratore della sicurezza, ad esempio `securityadmin@contoso.com`.  <br/> Se il messaggio di posta elettronica viene inviato da un dominio rappresentato: scegliere i **messaggi in quarantena**.  <br/> |
|Business intelligence della cassetta postale  <br/> |Per impostazione predefinita, business intelligence della cassetta postale è selezionata quando si crea un nuovo criterio di protezione anti-phishing. Lasciare l'impostazione **su** per ottenere risultati ottimali.<br/> |
|Aggiungere domini e mittenti attendibili  <br/> |In questo esempio, non definire le sostituzioni.  <br/> |
|Applicato a  <br/> |Selezionare **il dominio del destinatario**. In **ognuno di questi elementi**, seleziona **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome di dominio, ad esempio `contoso.com`, nell'elenco e quindi scegliere **Aggiungi**. Selezionare **Fine**.<br/> |
   
## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Eliminare un anti-phishing o dei criteri anti-phishing degli strumenti di analisi

È possibile eliminare criteri personalizzati creati utilizzando la protezione &amp; centro conformità. È possibile eliminare il criterio predefinito per l'organizzazione. È consigliabile utilizzare la sicurezza &amp; centro conformità per visualizzare o modificare i criteri degli strumenti di analisi.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio**, selezionare **criterio**.
    
3. Nella pagina **criteri** scegliere **Anti-phishing** o **degli strumenti di analisi anti-phishing**.
    
4. Nella pagina **protezione Anti-phishing** o **degli strumenti di analisi anti-phishing** , selezionare il nome del criterio dall'elenco.

5. Nella pagina visualizzata scegliere **eliminare criteri**. Consentire fino a 30 minuti per le modifiche apportate da distribuire a tutti i centri dati di Office 365.
    

## <a name="next-steps"></a>Passaggi successivi

Una volta criteri di anti-phishing, è possibile visualizzare la modalità di utilizzo delle funzionalità di protezione di rischio per l'organizzazione visualizzando i report. Le risorse seguenti per ulteriori informazioni, vedere:
- [Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md) o [visualizzare i report di protezione posta elettronica](view-email-security-reports.md)
- [Utilizzare Esplora (anche noto come rischio Explorer)](use-explorer-in-security-and-compliance.md)

Mantenersi in primo piano rispetto a nuove funzionalità di punta degli strumenti di analisi. visita il sito Web [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e informazioni sulle [nuove funzionalità che vengono aggiunti degli strumenti di analisi](office-365-atp.md#new-features-are-continually-being-added-to-atp).
 