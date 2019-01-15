---
title: Simulatore di attacchi in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/02/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: Amministratore globale di Office 365, è possibile utilizzare simulatore di attacco per l'esecuzione di scenari di attacco realistico all'interno dell'organizzazione. Ciò consente di identificare e trovare gli utenti vulnerabili prima di un attacco reale accede a un'azienda.
ms.openlocfilehash: 3449e29197aa5a7a0b63a805ad8cc429f8f8f81b
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015038"
---
# <a name="attack-simulator-in-office-365"></a>Simulatore di attacchi in Office 365

**Riepilogo** Se si è un amministratore globale di Office 365 e l'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md), è possibile utilizzare simulatore di attacco per l'esecuzione di scenari di attacco realistico all'interno dell'organizzazione. Ciò consente di identificare e individuare gli utenti vulnerabili prima di un attacco reale un impatto significativo sulla parte inferiore. In questo articolo per ulteriori informazioni.
  
## <a name="the-attacks"></a>Gli attacchi

Tre tipi di simulazioni attacco sono attualmente disponibili:
  
- [Attacco spear phishing nome di visualizzazione](attack-simulator.md#spearphish)
    
- [Attacco di tipo spray password](attack-simulator.md#passwordspray)
    
- [Attacchi di forza bruta attacco password](attack-simulator.md#bruteforce)
    
Per un attacco in cui deve essere avviato correttamente, si utilizza l'autenticazione a più fattori l'account utilizzato per eseguire gli attacchi di tipo simulati. Inoltre, è necessario essere un amministratore globale di Office 365.
  
> [!NOTE]
> Supporto per l'accesso condizionale saranno presto disponibili. 
  
Per accedere a simulatore di attacco, in sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che la propria organizzazione soddisfino i requisiti seguenti per simulatore di attacco di tipo:
      
- Messaggio di posta elettronica dell'organizzazione è ospitata in Exchange Online. (Simulatore di attacco di tipo non disponibile per i server di posta elettronica locale).
    
- Essere un amministratore globale di Office 365
    
- L'organizzazione utilizza [l'autenticazione a più fattori per gli utenti di Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)
 
- L'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md)con attacco simulatore visibili nella protezione &amp; centro conformità (Vai alla **gestione delle minacce** \> **simulatore di attacco**)<br/>![Gestione di rischio - simulatore di attacco](media/ThreatMgmt-AttackSimulator.png)

    
## <a name="display-name-spear-phishing-attack"></a>Attacco spear phishing nome di visualizzazione

Il phishing è un termine generico per un ampio gruppo di attacchi classificato come stile attacchi. Questo attacco viene trattata principalmente spear phishing, un attacco più mirato è destinato a un gruppo specifico di singoli utenti o un'organizzazione. In genere, eseguire un attacco personalizzato con alcuni esplorazione delle e utilizzando un nome visualizzato che genera relazione di trust in destinatario, ad esempio un messaggio di posta elettronica è simile a quello proviene da un dirigente all'interno dell'organizzazione.
  
Questo attacco è incentrata su che consente di modificare che viene visualizzato il messaggio di origine per la modifica dell'indirizzo di origine e nome visualizzato. Quando gli attacchi di phishing spear esito positivo, cybercriminali accedere alle credenziali degli utenti.
  
### <a name="to-simulate-a-spear-phishing-attack"></a>Per simulare un attacco di spear phishing

![Comporre corpo del messaggio di posta elettronica](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
È possibile creare l'editor HTML avanzata direttamente nel campo del **corpo del messaggio di posta elettronica** direttamente o lavorare con origine HTML.
  
1. Nella [protezione &amp; centro conformità](https://protection.office.com), scegliere **gestione rischio** \> **simulatore di attacco**.
    
2. Specificare un nome significativo campagna per l'attacco o selezionare un modello. <br/>![Pagina iniziale di phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Ogni destinatario di destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo. <br/>![Selezione dei destinatari](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. Configurare i dettagli di posta elettronica di Phishing. <br/>![Configurare i dettagli di posta elettronica](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/>La formattazione HTML può essere complessa o base quando la campagna le esigenze. Come formato di posta elettronica HTML, è possibile inserire immagini e testo per il miglioramento believability. È possibile specificare in quali il messaggio ricevuto come appare nel client di posta elettronica destinatario.
    
5. Specificare il testo del campo **da (Name)** . Questo è il campo che indica il **Nome visualizzato** nel client di posta elettronica destinatario. 
    
6. Consente di specificare il testo o il campo **da** . Questo è il campo che indica l'indirizzo di posta elettronica del mittente nel client di posta elettronica destinatario.<br/>È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo consentirà l'indirizzo di posta elettronica effettivamente risolvere nel client ricevente semplificazione un modello di protezione estremamente elevata), oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere, ma è necessario dopo il formato di un indirizzo SMTP valido, ad esempio user@domainname.extension. 
  
7. Utilizzando il selettore di riepilogo a discesa, selezionare un URL di server di accesso di Phishing che indica il tipo di contenuto che è necessario nell'attacco. URL con temi diversi, vengono forniti da scegliere, ad esempio documenti recapito tecnici, paghe e stipendi e così via. Si tratta in modo efficace l'URL assegnato agli utenti vengono chiesto di fare clic su.
    
8. Consente di specificare un URL della pagina di destinazione personalizzato. Utilizzando questo verrà reindirizzare gli utenti a un URL specificato alla fine di un attacco. Se si dispone di formazione interni, ad esempio, è possibile specificare che qui.
    
9. Specificare il testo per il campo **oggetto** . Questo è il campo che indica che il **Nome soggetto** nel client di posta elettronica destinatario. 
    
10. Comporre il **corpo del messaggio di posta elettronica** che riceverà la destinazione. <br/>`${username}`Inserisce il nome di destinazioni nel corpo del messaggio di posta elettronica. <br/>`${loginserverurl}`Inserisce l'URL che si desidera che gli utenti di destinazione fare clic su 
    
11. Scegliere **Avanti,** quindi **completare** per avviare l'attacco. Messaggio di posta elettronica spear phishing viene recapitato a cassette postali dei destinatari di destinazione. 
    
## <a name="password-spray-attack"></a>Attacco di tipo spray password

Un attacco di spray password in un'organizzazione viene utilizzato in genere dopo un attore bad ha acquisito un elenco di utenti validi dal tenant. Attore bad a conoscenza di password comuni che utenti utilizzo. Si tratta di un attacco ampiamente utilizzato come è un attacco di tipo economico esecuzione e più difficili da rilevare di forza bruta approcci.
  
Questo attacco è incentrata su che consente di specificare una password comune con una base di grandi dimensioni di destinazione di utenti.
  
### <a name="to-simulate-a-password-spray-attack"></a>Per simulare un attacco spray password

1. Nella [protezione &amp; centro conformità](https://protection.office.com), scegliere **gestione rischio** \> **simulatore di attacco**.
    
2. Specificare un nome significativo campagne un attacco.
    
3. Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.
    
4. Consente di specificare una password da utilizzare per l'attacco. Ad esempio, è una password comune, pertinenti è possibile provare `Fall2017`. Un altro potrebbe essere `Spring2018`, o `Password1`.
    
5. Scegliere **Fine** per avviare l'attacco. 
    
## <a name="brute-force-password-attack"></a>Attacchi di forza bruta attacco password

Un attacco di forza bruta password in un'organizzazione viene utilizzato in genere dopo un attore bad ha acquisito un elenco di utenti chiavi da tenant. Questo attacco è incentrata su cercando un set di password in un singolo account utente.
  
### <a name="to-simulate-a-brute-force-password-attack"></a>Per simulare un attacco di forza bruta password

1. Nella [protezione &amp; centro conformità](https://protection.office.com), scegliere **gestione rischio** \> **simulatore di attacco**.
    
2. Specificare un nome significativo campagne un attacco.
    
3. Consente di specificare il destinatario. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.
    
4. Specificare una password da utilizzare per l'attacco. A tale scopo, è possibile utilizzare un file di testo (con estensione txt) per l'elenco delle password. Il file di testo non può superare i 10 MB dimensioni file. Utilizzare una password per riga e assicurarsi di includere un ritorno dopo l'ultima password nell'elenco.
    
5. Scegliere **Fine** per avviare l'attacco. 
    
## <a name="new-features-in-attack-simulator"></a>Nuove funzionalità di simulatore di attacco

Nuove funzionalità vengono aggiunti simulatore di attacco. Tali strumenti comprendono:
- **Creazione di rapporti avanzate**. Sarà in grado di visualizzare i dati, ad esempio l'ora più veloce (o più lento) per aprire un messaggio di posta elettronica simulazione di attacco, l'ora più veloce (o più lento) fare clic su un collegamento nel messaggio e altro ancora.
- **Editor dei modelli di posta elettronica**. È possibile creare un modello di posta elettronica personalizzati e riutilizzabili che è possibile utilizzare per simulazioni attacchi futuri.

Visita il sito Web [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) per osservare le novità dello sviluppo di, che cos'è distribuzione e che cos'è già avviato.



