---
title: Simulatore di attacchi in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: In qualità di amministratore globale di Office 365, è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale colpisca la propria azienda.
ms.openlocfilehash: 25686ce194deca8d1ca07fca40f8142492951574
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410831"
---
# <a name="attack-simulator-in-office-365"></a>Simulatore di attacchi in Office 365

**Riepilogo** Se si è un amministratore globale di Office 365 e l'organizzazione dispone di [office 365 Threat Intelligence](office-365-ti.md), è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base. Leggere questo articolo per ulteriori informazioni.

> [!IMPORTANT]
> A partire da febbraio 2019 e distribuita nei prossimi mesi, Office 365 Threat Intelligence sta diventando Office 365 Advanced Threat Protection Plan 2, con ulteriori funzionalità di protezione dalle minacce. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).
  
## <a name="the-attacks"></a>Gli attacchi

Sono attualmente disponibili tre tipi di simulazioni di attacco:
  
- [Nome visualizzato Spear-attacco di phishing](attack-simulator.md#spearphish)
    
- [Attacco spray per la password](attack-simulator.md#passwordspray)
    
- [Attacco per la password con forza bruta](attack-simulator.md#bruteforce)
    
Per l'avvio di un attacco, è possibile utilizzare l'autenticazione a più fattori nell'account che si sta utilizzando per eseguire attacchi simulati. Inoltre, è necessario essere un amministratore globale di Office 365.
  
> [!NOTE]
> Il supporto per l'accesso condizionale è disponibile a breve. 
  
Per accedere a simulatore di attacco, &amp; nel centro sicurezza e conformità scegliere **Threat Management** \> **Attack Simulator**.
  
## <a name="before-you-begin"></a>Prima di iniziare...

Assicurarsi che l'utente e l'organizzazione soddisfino i seguenti requisiti per il simulatore di attacco:
      
- **La posta elettronica dell'organizzazione è ospitata in Exchange Online**. (Attack Simulator non è disponibile per i server di posta elettronica locali.)
    
- **Si è un amministratore globale di Office 365**
    
- L' ** [autenticazione](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide) a più fattori (AMF) è attivata, almeno per l'account amministratore globale di Office 365**. (Idealmente, l'AMF è attivata per tutti gli utenti dell'organizzazione.)
 
- **l'organizzazione dispone [di Office 365 threat Intelligence](office-365-ti.md)**, con simulatore di attacco visibile &amp; nel centro sicurezza e conformità (andare a **Threat management** \> **Attack simulator**)<br/>![Threat Management-simulatore d'attacco](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>Nome visualizzato Spear-attacco di phishing

Il phishing è un termine generico per una vasta serie di attacchi classificati come un attacco stile di social engineering. Questo attacco è concentrato sul phishing Spear, un attacco più mirato che si rivolge a un gruppo specifico di persone o di un'organizzazione. In genere, un attacco personalizzato con alcuni ricognizione eseguito e utilizzando un nome visualizzato che genererà la fiducia nel destinatario, ad esempio un messaggio di posta elettronica che sembra provenire da un dirigente all'interno dell'organizzazione.
  
Questo attacco è incentrato sull'eventualità di modificare il messaggio a cui sembra abbia avuto origine cambiando il nome visualizzato e l'indirizzo di origine. Quando gli attacchi Spear-phishing hanno esito positivo, i criminali informatici accedono alle credenziali degli utenti.
  
### <a name="to-simulate-a-spear-phishing-attack"></a>Per simulare un attacco di Spear-phishing

![Comporre il corpo della posta elettronica](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
È possibile creare l'editor HTML RTF direttamente nel campo **corpo del messaggio di posta elettronica** o collaborare con l'origine HTML.
  
1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.
    
2. Specificare un nome di campagna significativo per l'attacco o selezionare un modello. <br/>![Pagina iniziale di phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. Specificare i destinatari di destinazione. Può trattarsi di singoli o gruppi nell'organizzazione. Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo. <br/>![Selezione destinatario](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. Configurare i dettagli di posta elettronica di phishing. <br/>![Configurare i dettagli della posta elettronica](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>La formattazione HTML può essere complessa o di base come necessario per la campagna. Poiché il formato del messaggio di posta elettronica è HTML, è possibile inserire immagini e testo per migliorare la credibilità. È possibile controllare l'aspetto del messaggio ricevuto nel client di posta elettronica di ricezione.
    
5. Specificare il testo per il campo **from (Name)** . Si tratta del campo che viene visualizzato nel **nome visualizzato** nel client di posta elettronica di ricezione. 
    
6. Specificare il testo o il campo **da** . Si tratta del campo che viene visualizzato come indirizzo di posta elettronica del mittente nel client di posta elettronica di ricezione. <br/>È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo l'indirizzo di posta elettronica viene effettivamente risolto nel client di ricezione, facilitando un modello di attendibilità molto elevato) oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere effettivamente, ma ha bisogno di seguire il formato di un indirizzo SMTP valido, ad esempio User @ NomeDominio. Extension. 
  
7. Usando il selettore a discesa, selezionare un URL del server di accesso di phishing che rispecchi il tipo di contenuto che si avrà all'interno dell'attacco. È possibile scegliere tra diversi URL a tema, ad esempio recapito dei documenti, tecnico, retribuzione e così via. Questo è effettivamente l'URL a cui gli utenti designati devono fare clic.
    
8. Specificare un URL della pagina di destinazione personalizzata. In questo modo gli utenti verranno reindirizzati a un URL specificato al termine di un attacco con esito positivo. Se si dispone di un training di sensibilizzazione interno, ad esempio, è possibile specificarlo qui.
    
9. Specificare il testo per il campo **Subject** . Si tratta del campo che viene visualizzato come **nome del soggetto** nel client di posta elettronica di ricezione. 
    
10. Comporre il **corpo del messaggio di posta elettronica** che riceverà il destinatario. <br/>`${username}`inserisce il nome della destinazione nel corpo della posta elettronica. <br/>`${loginserverurl}`inserisce l'URL in cui si desidera che gli utenti di destinazione clicchino 
    
11. Fare clic su **Avanti,** quindi su **fine** per avviare l'attacco. Il messaggio di posta elettronica di phishing Spear viene recapitato alle cassette postali dei destinatari. 
    
## <a name="password-spray-attack"></a>Attacco spray per la password

Un attacco di spruzzatura della password in un'organizzazione viene in genere utilizzato dopo che un attore cattivo ha acquisito un elenco di utenti validi dal tenant. L'attore cattivo conosce le password comuni utilizzate dalle persone. Si tratta di un attacco ampiamente utilizzato, poiché si tratta di un attacco a basso costo da eseguire e più difficile da rilevare rispetto alla forza bruta.
  
Questo attacco consente di specificare una password comune rispetto a una base di utenti di grandi dimensioni.
  
### <a name="to-simulate-a-password-spray-attack"></a>Per simulare un attacco spray per la password

1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.
    
2. Specificare il nome di una campagna significativa per l'attacco.
    
3. Specificare i destinatari di destinazione. Può trattarsi di singoli o gruppi nell'organizzazione. Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.
    
4. Specificare una password da utilizzare per l'attacco. Ad esempio, una password comune e pertinente che è possibile `Fall2017`provare è. Un altro potrebbe `Spring2018`essere, `Password1`o.
    
5. Scegliere **fine** per avviare l'attacco. 
    
## <a name="brute-force-password-attack"></a>Attacco per la password con forza bruta

Un attacco di password con forza bruta nei confronti di un'organizzazione viene in genere utilizzato dopo che un attore non valido ha acquisito un elenco di utenti chiave dal tenant. Questo attacco si concentra sul tentativo di un set di password su un singolo account utente.
  
### <a name="to-simulate-a-brute-force-password-attack"></a>Per simulare un attacco di password con forza bruta

1. Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.
    
2. Specificare il nome di una campagna significativa per l'attacco.
    
3. Specificare il destinatario di destinazione. Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.
    
4. Specificare un set di password da utilizzare per l'attacco. A tale scopo, è possibile utilizzare un file di testo (con estensione txt) per l'elenco delle password. Il file di testo non può superare i 10 MB nelle dimensioni dei file. Utilizzare una password per riga e assicurarsi di includere un ritorno a capo dopo l'ultima password dell'elenco.
    
5. Scegliere **fine** per avviare l'attacco. 
    
## <a name="new-features-in-attack-simulator"></a>Nuove funzionalità in Attack Simulator

Sono state aggiunte nuove funzionalità al simulatore di attacco. Queste funzionalità sono:

- **Funzionalità di creazione di report avanzate**. È possibile visualizzare i dati, ad esempio il tempo più rapido (o più lento) per aprire un messaggio di posta elettronica di simulazione di attacco, ovvero il tempo più rapido (o più lento) per fare clic su un collegamento nel messaggio e altro ancora.

- **Editor modelli di posta elettronica**. È possibile creare un modello di posta elettronica personalizzato e riutilizzabile che è possibile utilizzare per simulazioni di attacco future.

Visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per vedere cosa c'è in sviluppo, cosa è in uscita e cosa è già stato avviato.

## <a name="see-also"></a>Vedere anche

[Office 365 Advanced Threat Protection Service Descrizione](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[Office 365 Advanced Threat Protection](office-365-atp.md)



