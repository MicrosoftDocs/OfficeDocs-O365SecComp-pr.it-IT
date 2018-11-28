---
title: Impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: Impostare i criteri di collegamenti sicuro per proteggere l'organizzazione da dannosi collegamenti nei file di Word, Excel, PowerPoint e Visio, nonché nei messaggi di posta elettronica.
ms.openlocfilehash: fb2af8e29bfe2de027a2d0e88cf9bcc07299fba9
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706090"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti

[Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md) , una funzionalità di [Protezione di Office 365 avanzate rischio](office-365-atp.md) degli (strumenti di analisi), consentono di proteggere l'organizzazione da dannosi collegamenti utilizzati in altri attacchi e phishing. Se si dispone di volte necessario [le autorizzazioni per la protezione di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md), è possibile impostare i criteri degli strumenti di analisi collegamenti attendibili per garantire che quando gli utenti fare clic su indirizzi web (URL), l'organizzazione è protetto. I criteri degli strumenti di analisi collegamenti attendibili possono essere configurati per analizzare gli URL nella posta elettronica ed nei documenti di Office.
  
[Nuove funzionalità vengono aggiunti continuamente a strumenti di analisi](office-365-atp.md#new-features-are-continually-being-added-to-atp). Con l'aggiunta di nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri degli strumenti di analisi provvisoria collegamenti esistenti.

## <a name="what-to-do"></a>cosa fare 
  
1. [Verificare i prerequisiti](#review-the-prerequisites).
    
2. [Revisione e modifica il criterio degli strumenti di analisi collegamenti sicuro predefinito che si applica a tutti gli utenti](#define-an-atp-safe-links-policy-that-applies-to-everyone). Ad esempio, è possibile [configurare l'elenco degli URL bloccato personalizzato per i collegamenti sicuro degli strumenti di analisi](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Aggiungere o modificare i criteri per i destinatari di posta elettronica specifico](#add-a-policy-for-specific-email-recipients), inclusa [l'impostazione di personalizzata "non di riscrittura" URL elenco per i collegamenti sicuro degli strumenti di analisi](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. [Informazioni sulle opzioni dei criteri degli strumenti di analisi collegamenti sicuri](#learn-about-atp-safe-links-policy-options) (in questo articolo), incluse le impostazioni per le modifiche recenti
    
## <a name="step-1-review-the-prerequisites"></a>Passaggio 1: Verificare i prerequisiti

- Verificare che l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md).
    
- Verificare di disporre delle autorizzazioni necessarie per definire o modificare i criteri degli strumenti di analisi. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).

- Verificare che i client di Office sono configurati per utilizzare [L'autenticazione moderno](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (sia per la protezione degli strumenti di analisi provvisoria collegamenti nei documenti di Office).
    
- [Informazioni sulle opzioni dei criteri degli strumenti di analisi collegamenti sicuri](#learn-about-atp-safe-links-policy-options) (in questo articolo). 

- Consentire fino a 30 minuti per il criterio di nuovo o aggiornato da distribuire a tutti i centri dati di Office 365.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Passaggio 2: Definire (o per prendere visione) il criterio degli strumenti di analisi collegamenti attendibili che si applica a tutti gli utenti

Quando si dispone di [Office 365 avanzate Threat Protection](office-365-atp.md), sarà necessario un criterio di collegamenti sicuro degli strumenti di analisi predefinito che si applica a tutti gli utenti nell'organizzazione. Assicurarsi di esaminare e, se necessario, modificare il criterio predefinito.
  
1. Accedere a [https://security.microsoft.com](https://security.microsoft.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio**, scegliere **criteri \> ** **Collegamenti sicuri**.
    
3. Nella sezione **criteri che si applicano all'intera organizzazione** , selezionare **predefinito**e quindi fare clic su **Modifica** (pulsante Edit a forma di una matita).<br/>![Fare clic su Modifica per modificare il criterio predefinito per la protezione collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Nella sezione **bloccare gli URL seguenti** , specificare uno o più URL che si desidera impedire agli utenti dell'organizzazione di visitare il sito. Vedere [configurazione di un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
5. Nella sezione **impostazioni che si applicano al contenuto, ad eccezione di posta elettronica** selezionare oppure deselezionare le opzioni che si desidera utilizzare. (È consigliabile selezionare tutte le opzioni). 
    
6. Scegliere **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Passaggio 3: Aggiungere (o modifica) degli strumenti di analisi collegamenti sicuri i criteri applicati ai destinatari di posta elettronica specifici

Dopo aver esaminato (o modificati) il criterio degli strumenti di analisi collegamenti sicuro predefinito che si applica a tutti gli utenti, il passaggio successivo consiste nel definire ulteriori criteri applicabili a destinatari specifici. Ad esempio, è possibile specificare eccezioni per il criterio predefinito mediante la definizione di un criterio aggiuntivo. 
  
1. Accedere a [https://security.microsoft.com](https://security.microsoft.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio**, selezionare **criterio**.
    
3. Scegliere **collegamenti sicuri**.
    
4. Nella sezione **criteri che si applicano a destinatari specifici** fare clic su **Nuovo** (pulsante nuovo simile a un segno di addizione ( **+**)).<br/>![Selezionare nuovo per aggiungere un criterio di collegamenti sicuro per i destinatari di posta elettronica specifico](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Specificare il nome, la descrizione e le impostazioni per il criterio.<br/>**Esempio:** Per configurare un criterio non denominato "diretto clickthrough" che non consente agli utenti in un determinato gruppo all'interno dell'organizzazione a fare clic per un sito Web specifico senza protezione degli strumenti di analisi collegamenti sicuri, è possibile specificare le seguenti impostazioni consigliate: 
    
  - Nella casella **nome** non digitare alcun clickthrough diretto.
    
  - Nella casella **Descrizione** digitare una descrizione come partecipanti impedisce determinati gruppi da facendo clic su tramite di un sito Web senza verifica degli strumenti di analisi collegamenti sicuri.
    
  - Nella sezione **Selezionare l'azione** , fare clic **su**.
    
  - Selezionare **Gli allegati sicuri di utilizzo per analizzare contenuto scaricabile**.
    
  - Se questa opzione è disponibile, selezionare **Applica sicuri collegamenti ai messaggi inviati all'interno dell'organizzazione**.
    
  - Selezionare **non consentire utente fare clic su tramite URL originale**.
    
  - (È facoltativo) Nella sezione **non riscrivere gli URL seguenti** , specificare uno o più URL sono considerati attendibili per l'organizzazione. (Vedere [configurare un personalizzato elenco URL "non di riscrittura" utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - Nella sezione **Applicato a** scegliere **il destinatario è un membro del**e quindi fare clic su gruppi di cui che si desidera includere nel criterio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
6. Scegliere **Save**.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Passaggio 4: Informazioni sulle opzioni di criteri di collegamenti sicuro degli strumenti di analisi

Come si consente di impostare o modificare i criteri degli strumenti di analisi collegamenti sicuro, verrà visualizzato sono disponibili diverse opzioni. Nel caso in cui sono chiedendo tali opzioni, nella tabella seguente vengono descritti ciascuno di essi e degli effetti. Tenere presente che esistono due tipi principali di criteri di collegamenti sicuro degli strumenti di analisi definire o modificare:
- un [criterio predefinito](#default-policy-options) che si applica a tutti gli utenti 
- altri [criteri definiti per destinatari specifici](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Opzioni dei criteri predefiniti

Opzioni dei criteri predefiniti si applicano a tutti gli utenti nell'organizzazione.

|Questa opzione  |Produce questo risultato  |
|---------|---------|
| **Bloccare gli URL seguenti** <br/>    | Consente all'organizzazione di disporre di un elenco personalizzato di URL che vengono bloccati automaticamente. Quando l'utente sceglie un URL interno dell'elenco, sarà da eseguire a una [pagina di avviso](atp-safe-links-warning-pages.md) che spiega perché l'URL è bloccato.<br/> Per ulteriori informazioni, vedere [impostazione e gestione di un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri      |
| **Office 365 ProPlus, Office per iOS e Android** <br/>    | Quando questa opzione è selezionata, degli strumenti di analisi collegamenti sicuro protezione viene applicata agli URL nei documenti presenti in Office 365 ProPlus (Word, Excel e PowerPoint in Windows o Mac OS), Office documenti aperti in iOS o dispositivi Android, 2016 di Visio in Windows e Office Online (Word Online, in linea di PowerPoint, Excel Online e OneNote Online), fornita che l'utente ha effettuato l'accesso a Office 365. <br/><br/>Se viene visualizzata solo **2016 di Office in Windows**, quindi gli aggiornamenti delle funzionalità non hanno raggiunto l'ambiente Office 365 ancora (e disponibile a breve). Nel frattempo, protezione degli strumenti di analisi collegamenti sicuro si applica a Word 2016, 2016 Excel, PowerPoint 2016 o 2016 di Visio in esecuzione su Windows.            |
| **Non registrare gli utenti di fare clic sui collegamenti sicuro degli strumenti di analisi** <br/>  | Quando questa opzione è selezionata, fare clic su dati per gli URL nei documenti di Word, Excel, PowerPoint e Visio non viene archiviato.  <br/> |
|**Non consentire agli utenti di fare clic su tramite degli strumenti di analisi collegamenti sicuro all'URL originale** <br/> |Quando questa opzione è selezionata, gli utenti non possono procedere oltre un [messaggio di avviso](atp-safe-links-warning-pages.md) per un URL che deve essere dannoso.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>I criteri applicati ai destinatari di posta elettronica specifico

|Questa opzione  |Produce questo risultato  |
|---------|---------|
|**Off** <br/> |Non analizza gli URL in messaggi di posta elettronica.  <br/> Consente di definire una regola di eccezione, ad esempio una regola che non analizza gli URL in messaggi di posta elettronica per un gruppo di destinatari specifico.  <br/> |
|**In** <br/> |Riscrittura URL agli utenti di route tramite protezione degli strumenti di analisi collegamenti sicuri quando gli utenti fare clic su URL nei messaggi di posta elettronica.  <br/> Controlla un URL quando si fa clic su un elenco di domini bloccati o dannoso URL.  <br/> |
|**Utilizzare gli allegati sicuri per analizzare contenuto scaricabile** <br/> |Quando questa opzione è selezionata, gli URL che puntano a informazioni sul contenuto scaricabile vengono analizzati.  <br/> |
|**Applicare sicuri collegamenti ai messaggi inviati all'interno dell'organizzazione** <br/> | Quando questa opzione è selezionata e disponibile, protezione degli strumenti di analisi collegamenti sicuro viene applicata alla posta elettronica i messaggi inviati tra utenti all'interno dell'organizzazione, fornito gli account di posta elettronica sono ospitati in Office 365.  <br/> |
|**Non viene registrata l'utente fa clic su** <br/> |Quando questa opzione è selezionata, fare clic su dati per gli URL nella posta elettronica da mittenti esterni non vengono archiviate. Fare clic su URL il rilevamento di collegamenti nei messaggi di posta elettronica inviati all'interno dell'organizzazione non è attualmente supportato.  <br/> |
|**Non consentire agli utenti di fare clic per URL originale** <br/> |Quando questa opzione è selezionata, gli utenti non possono procedere oltre un [messaggio di avviso](atp-safe-links-warning-pages.md) per un URL che deve essere dannoso.  <br/> |
|**Non riscrivere gli URL seguenti** <br/> |Lascia URL quelli specificati. Consente di mantenere un elenco personalizzato di URL sicuro che non hanno bisogno di virus per un gruppo specifico di destinatari di posta elettronica nell'organizzazione.  Per ulteriori informazioni, incluse le modifiche recenti per il supporto per un carattere jolly asterisco, vedere [configurare un personalizzato elenco URL "non di riscrittura" utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) (\*).<br/> |
   
## <a name="next-steps"></a>Passaggi successivi

Una volta i criteri degli strumenti di analisi collegamenti sicuri, è possibile visualizzare la modalità di utilizzo degli strumenti di analisi per il non esiste visualizzando i report. Le risorse seguenti per ulteriori informazioni, vedere:

- [Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)

- [Utilizzare Esplora in sicurezza &amp; centro conformità](use-explorer-in-security-and-compliance.md) 