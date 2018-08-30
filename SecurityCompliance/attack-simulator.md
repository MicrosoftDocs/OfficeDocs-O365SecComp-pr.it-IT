---
title: Simulatore di attacchi in Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: Informazioni su tre diversi tipi di attacchi cyber che è possibile eseguire utilizzando simulatore di attacco.
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530535"
---
# <a name="attack-simulator-in-office-365"></a>Simulatore di attacchi in Office 365

Con attacco simulatore (incluso in [Office 365 rischio Intelligence](office-365-ti.md)), se non è un membro del team di protezione dell'organizzazione, è possibile eseguire scenari di attacco realistico all'interno dell'organizzazione. Ciò consente di identificare e individuare gli utenti vulnerabili prima di un attacco reale un impatto significativo sulla parte inferiore.
  
## <a name="the-attacks"></a>Gli attacchi

Alla versione preview è sono disponibili tre tipi di simulazioni attacco che è possibile eseguire:
  
- [Attacco spear phishing nome di visualizzazione](attack-simulator.md#spearphish)
    
- [Attacco di tipo spray password](attack-simulator.md#passwordspray)
    
- [Attacchi di forza bruta attacco password](attack-simulator.md#bruteforce)
    
Per un attacco in cui deve essere avviato correttamente, l'account che esegue l'attacco e viene eseguito l'accesso deve utilizzare l'autenticazione a più fattori.
  
> [!NOTE]
> Supporto per l'accesso condizionale saranno presto disponibili. 
  
Per accedere a simulatore di attacco, in sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che la propria organizzazione soddisfino i requisiti seguenti per simulatore di attacco di tipo:
  
- L'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md)con attacco simulatore visibili nella protezione &amp; centro conformità (Vai alla **gestione delle minacce** \> **simulatore di attacco**)
    
- Messaggio di posta elettronica dell'organizzazione è ospitata in Exchange Online. (Simulatore di attacco di tipo non disponibile per i server di posta elettronica locale).
    
- Essere un amministratore globale di Office 365
    
- L'organizzazione utilizza [l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="display-name-spear-phishing-attack"></a>Attacco spear phishing nome di visualizzazione

Il phishing è un termine generico per un ampio gruppo di attacchi classificato come stile attacchi. Questo attacco viene trattata principalmente spear phishing, un attacco più mirato è destinato a un gruppo specifico di singoli utenti o un'organizzazione. In genere, eseguire un attacco personalizzato con alcuni esplorazione delle e utilizzando un nome visualizzato che genera relazione di trust in destinatario, ad esempio un messaggio di posta elettronica è simile a quello proviene da un dirigente all'interno dell'organizzazione.
  
Questo attacco è incentrata su che consente di modificare che viene visualizzato il messaggio di origine per la modifica dell'indirizzo di origine e nome visualizzato. Quando gli attacchi di phishing spear esito positivo, cybercriminali accedere alle credenziali degli utenti.
  
### <a name="to-simulate-a-spear-phishing-attack"></a>Per simulare un attacco di spear phishing

![Comporre corpo del messaggio di posta elettronica](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
È possibile creare l'editor HTML avanzata direttamente nel campo del **corpo del messaggio di posta elettronica** direttamente o lavorare con origine HTML. Esistono due campi importanti per l'inclusione in HTML: 
  
1. In sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.
    
2. Specificare un nome significativo campagna per l'attacco o selezionare un modello.
    
    ![Pagina iniziale di phishing](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.
    
    ![Selezione dei destinatari](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. Configurare i dettagli di posta elettronica di Phishing.
    
    ![Configurare i dettagli di posta elettronica](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    La formattazione HTML può essere complessa o base quando la campagna le esigenze. Come HTML, è possibile inserire immagini e testo per il miglioramento believability. È possibile specificare in quali il messaggio ricevuto come appare nel client di posta elettronica destinatario.
    
1. Immettere il testo del campo **da (Name)** . Questo è il campo che indica il **Nome visualizzato** nel client di posta elettronica destinatario. 
    
2. Immettere il testo o il campo **da** . Questo è il campo che indica l'indirizzo di posta elettronica del mittente nel client di posta elettronica destinatario. 
    
    > [!IMPORTANT]
    > È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo consentirà l'indirizzo di posta elettronica effettivamente risolvere nel client ricevente semplificazione un modello di protezione estremamente elevata), oppure è possibile immettere un indirizzo di posta elettronica esterno. L'indirizzo di posta elettronica specificato non deve esistere, ma è necessario dopo il formato di un indirizzo SMTP valido, ad esempio user@domainname.extension. 
  
3. Utilizzando il selettore di riepilogo a discesa, selezionare un URL di server di accesso di Phishing che indica il tipo di contenuto che è necessario nell'attacco. URL con temi diversi, vengono forniti da scegliere, ad esempio documenti recapito tecnici, paghe e stipendi e così via. Si tratta in modo efficace l'URL assegnato agli utenti vengono chiesto di fare clic su.
    
4. Immettere l'URL di una pagina di destinazione personalizzato. Utilizzando questo verrà reindirizzare gli utenti a un URL specificato alla fine di un attacco. Se si dispone di formazione interni, ad esempio, è possibile specificare che qui.
    
5. Immettere il testo nel campo **oggetto** . Questo è il campo che indica che il **Nome soggetto** nel client di posta elettronica destinatario. 
    
5. Comporre il **corpo del messaggio di posta elettronica** che riceverà la destinazione. 
  
 **${username}** inserisce il nome di destinazioni nel corpo del messaggio di posta elettronica 
  
 **${loginserverurl}** inserisce l'URL che si desidera che gli utenti di destinazione fare clic su 
    
6. Scegliere **Avanti,** quindi **completare** per avviare l'attacco. Messaggio di posta elettronica spear phishing viene recapitato a cassette postali dei destinatari di destinazione. 
    
## <a name="password-spray-attack"></a>Attacco di tipo spray password

Un attacco di spray password in un'organizzazione viene utilizzato in genere dopo un attore bad correttamente i valori enumerati un elenco di utenti validi dal tenant, utilizzando le proprie conoscenze di password comuni utilizzati. È utilizzata frequentemente come è un attacco di tipo economico per l'esecuzione e più difficili da rilevare di forza bruta approcci.
  
Questo attacco è incentrata su che consente di specificare una password comune con una base di grandi dimensioni di destinazione di utenti.
  
### <a name="to-simulate-a-password-spray-attack"></a>Per simulare un attacco spray password

1. In sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.
    
2. Specificare un nome significativo campagne un attacco.
    
3. Consente di specificare i destinatari di destinazione. Può trattarsi di singoli utenti o gruppi all'interno dell'organizzazione. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.
    
4. Consente di specificare una password da utilizzare per l'attacco. Ad esempio, è una password comune, pertinenti è possibile provare `Fall2017`. Un altro potrebbe essere `Spring2018`, o `Password1`.
    
5. Scegliere **Fine** per avviare l'attacco. 
    
## <a name="brute-force-password-attack"></a>Attacchi di forza bruta attacco password

Un attacco di forza bruta password in un'organizzazione viene utilizzato in genere dopo un attore bad correttamente i valori enumerati un elenco di utenti chiavi da tenant. Questo attacco è incentrata su che consente di specificare un set di password con un singolo utente.
  
### <a name="to-simulate-a-brute-force-password-attack"></a>Per simulare un attacco di forza bruta password

1. In sicurezza &amp; centro conformità, scegliere **gestione rischio** \> **simulatore di attacco**.
    
2. Specificare un nome significativo campagne un attacco.
    
3. Consente di specificare il destinatario. Un destinatario destinazione deve essere Online cassetta postale di Exchange in modo che l'attacco abbia esito positivo.
    
4. Specificare una password da utilizzare per l'attacco. Ad esempio, è una password comune, pertinenti è possibile provare `Fall2017`. Un altro potrebbe essere `Spring2018`, o `Password1`.
    
5. Scegliere **Fine** per avviare l'attacco. 
    
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Threat Intelligence](office-365-ti.md)
  

