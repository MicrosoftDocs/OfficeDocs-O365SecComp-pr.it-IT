---
title: Secure Score di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: Come mai il livello di protezione dell'organizzazione effettivamente presente in Office 365? Punteggio sicura è qui Guida in linea. Punteggio sicura analizza la protezione dell'organizzazione in base alle normali attività e le impostazioni di sicurezza in Office 365 e assegna un punteggio.
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559089"
---
# <a name="office-365-secure-score"></a>Secure Score di Office 365

**Riepilogo** Come mai il livello di protezione dell'organizzazione effettivamente presente in Office 365? Punteggio sicura è qui Guida in linea. Punteggio sicura analizza la protezione dell'organizzazione in base alle normali attività e le impostazioni di sicurezza in Office 365 e assegna un punteggio. In questo articolo per una panoramica di punteggio sicura e su come è possibile utilizzarlo.
  
## <a name="how-to-get-to-secure-score"></a>Come ottenere sicura punteggio

Se l'organizzazione dispone di una sottoscrizione che include [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/)o Business Premium di Office 365 e si dispone delle [autorizzazioni necessarie](#required-permissions), è possibile visualizzare punteggio protette della propria organizzazione, visitare il sito [https://securescore.office.com](https://securescore.office.com). 

In alternativa, è possibile visitare il centro conformità di & protezione ([https://protection.office.com](https://protection.office.com)), dove troverai un widget punteggio sicuro che offre il punteggio corrente.

![Secure widget punteggio](media/SecureScoreWidget-o365.png)

Widget include un collegamento al dashboard punteggio sicura.

![Secure punteggio dashboard](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>Funzionamento

Punteggio sicura determina quali servizi di Office 365 in uso (ad esempio, OneDrive, SharePoint ed Exchange) quindi confronta le impostazioni e delle attività alla linea di base stabilita da Microsoft. Verrà visualizzato un punteggio in base alla modalità allineata in modo corretto nell'organizzazione è con suggerimenti per la protezione. Verranno inoltre presentati suggerimenti sulla procedura da eseguire per migliorare il punteggio dell'organizzazione. 
  
![Coda di azioni nello strumento di Office 365 sicura punteggio](media/SecureScore-ActionsToTake.png)
  
Punteggio sicura calcola il punteggio in base ai servizi che è stato acquistato. Se è stato acquistato solo un piano di Exchange Online, non sarà ad esempio, essere catalogato per la funzionalità di sicurezza di SharePoint Online. Denominatore del punteggio di è la somma di tutte le linee di base per i controlli che si applicano ai prodotti che è stato acquistato. Numeratore è la somma di tutti i controlli di cui è completata o completata parzialmente, le azioni per soddisfare tale controllo.

Espandere un'azione per conoscere i passaggi da eseguire, le minacce che saranno utili protezione da e il numero di punti punteggio aumenterà dopo che è seguire i suggerimenti.
  
![Azione espansa nello strumento di Office 365 sicura punteggio](media/SecureScore-DetailedActionToTake.png)
  
Per visualizzare l'impatto delle proprie azioni in sicurezza della propria organizzazione, selezionare la scheda **Punteggio Analyzer** e rivedere la cronologia delle. 
  
![Scheda Analyzer punteggio dello strumento di Office 365 sicura punteggio](media/SecureScore-ScoreAnalyzer-7days.png)
  
Sotto il grafico verrà visualizzato un elenco di punteggi e azioni in base alla categoria. 
  
![Grafico della scheda Analyzer punteggio con un punto di dati selezionato](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
Azioni che sono contrassegnate come **[Non catalogato]** sono quelle eseguibili per l'organizzazione, ma poiché non sono connessi al punteggio sicura, non sono catalogati.  

Nella pagina **Analizzatore di punteggio** , fare clic su un punto di dati per un giorno specifico, quindi scorrere verso il basso per vedere le azioni completate e da completare per quel giorno scoprire quali modificate. Il punteggio viene calcolato una volta al giorno (circa 1:00 AM PST). Se si apporta una modifica a un'azione misurata, il punteggio verrà aggiornati automaticamente il giorno successivo. Accetta un massimo di 48 ore essere presi in punteggio una modifica.

Punteggio sicura non express una misura assoluta della probabilità che verranno ottenere superata. Consente di rappresentare l'estensione a cui si hanno adottato caratteristiche che consentono di compensare i rischi di viene superata. Nessun servizio può garantire che non essere superata e punteggio sicura non deve essere interpretato come una garanzia in alcun modo.
 
## <a name="how-secure-score-helps"></a>Come aiuta a proteggere punteggio

Con punteggio sicura, è possibile migliorare condizioni di protezione dell'organizzazione utilizzando le funzionalità di protezione predefinite in Office 365 (molte delle quali già acquistato, ma potrebbe non essere presente). Informazioni approfondite su tali funzionalità consentono la massima di ricordare che verrà affidata la procedura appropriata per proteggere l'organizzazione da minacce.
  
Ma semplicemente provate per tale. Clienti che utilizzano sicura punteggio hanno registrato il punteggio di aumentare i clienti che non utilizzano lo stato coinvolge cinque volte. Il l'aumento della loro punteggio corrisponde con le funzionalità di sicurezza in uso nelle loro organizzazioni.
  
> [!NOTE]
> Punteggio sicura non express una misura assoluta della probabilità che verranno ottenere superata. Consente di rappresentare l'estensione a cui si hanno adottato controlli che consentono di compensare il rischio che viene superata. Nessun servizio può garantire che non essere superata e sicura punteggio non deve essere interpretato come una garanzia in alcun modo. 
  
## <a name="required-permissions"></a>Autorizzazioni necessarie

Per visualizzare e utilizzare il dashboard di punteggio sicura, è necessario essere assegnato uno dei seguenti ruoli di Azure Active Directory:
- Amministratore globale
- Amministratore fatturazione
- Amministratore utenti
- Amministratore password
- Amministratore della sicurezza
- Lettore di sicurezza
- Amministrazione di Exchange
- Amministratore di SharePoint

 Gli utenti non assegnati a un ruolo di amministratore non saranno in grado di accedere punteggio sicura.

## <a name="related-topics"></a>Argomenti correlati

[Panoramica della sicurezza di dashboard](security-dashboard.md)

[Qual è l’abbonamento corrente?](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)