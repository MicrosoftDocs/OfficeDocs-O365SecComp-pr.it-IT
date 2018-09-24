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
ms.openlocfilehash: f1b5ca193043c5fffdcf5e2dee21a08f388fdcdf
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972308"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti

[Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md) , una funzionalità di [Protezione di Office 365 avanzate rischio](office-365-atp.md) degli (strumenti di analisi), consentono di proteggere l'organizzazione da dannosi collegamenti utilizzati in altri attacchi e phishing. Se si dispone di volte necessario [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md), è possibile impostare i criteri degli strumenti di analisi collegamenti attendibili per garantire che quando gli utenti fare clic su indirizzi web (URL), l'organizzazione è protetto. I criteri degli strumenti di analisi collegamenti attendibili possono essere configurati per analizzare gli URL nella posta elettronica ed nei documenti di Office.
  
Nuove funzionalità vengono aggiunti continuamente ai collegamenti sicuro degli strumenti di analisi:
  
- In ritardo ottobre 2017, protezione degli strumenti di analisi collegamenti sicuro viene esteso per applicare all'URL di posta elettronica e gli URL nei documenti di Office 365 ProPlus, ad esempio Word, Excel, PowerPoint in Windows, iOS e dispositivi Android e i file di Visio in Windows.
    
- A partire da marzo 2018 protezione degli strumenti di analisi collegamenti sicuro viene estesa da applicare alla posta elettronica inviato tra utenti dell'organizzazione.
    
- A partire da ritardo 2018 marzo, protezione degli strumenti di analisi collegamenti sicuro viene estesa per applicare agli URL in Office Online (Online di Word, Excel Online, in linea di PowerPoint e OneNote Online) e Office 365 ProPlus in Mac OS.
    
- A partire da maggio 2018 [avviso pagine](atp-safe-links-warning-pages.md) vengono aggiornate con una nuova combinazione di colori, ulteriori informazioni e la possibilità di continuare a un sito nonostante i suggerimenti di carattere specificati. 

Con l'aggiunta di nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri degli strumenti di analisi provvisoria collegamenti esistenti.

## <a name="what-to-do"></a>cosa fare 
  
1. [Verificare i prerequisiti](#review-the-prerequisites).
    
2. [Revisione e modifica il criterio degli strumenti di analisi collegamenti sicuro predefinito che si applica a tutti gli utenti](#define-an-atp-safe-links-policy-that-applies-to-everyone). Ad esempio, è possibile [configurare l'elenco degli URL bloccato personalizzato per i collegamenti sicuro degli strumenti di analisi](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Aggiungi un criterio per i destinatari di posta elettronica specifico](#add-a-policy-for-specific-email-recipients), inclusa [l'impostazione di personalizzata "non di riscrittura" URL elenco per i collegamenti sicuro degli strumenti di analisi](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. [Informazioni sulle opzioni dei criteri degli strumenti di analisi collegamenti sicuri](#learn-about-atp-safe-links-policy-options) (in questo articolo), incluse le impostazioni per le modifiche recenti
    
## <a name="review-the-prerequisites"></a>Verificare i prerequisiti

- Verificare che l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md).
    
- Verificare di disporre delle autorizzazioni necessarie per definire o modificare i criteri degli strumenti di analisi. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
    
- [Informazioni sulle opzioni dei criteri degli strumenti di analisi collegamenti sicuri](#learn-about-atp-safe-links-policy-options) (in questo articolo). 

- Verificare che i client di Office siano configurati per utilizzare [L'autenticazione moderno](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).
    
- Consentire fino a 30 minuti per il criterio di nuovo o aggiornato da distribuire a tutti i centri dati di Office 365.
    
## <a name="define-an-atp-safe-links-policy-that-applies-to-everyone"></a>Definire un criterio degli strumenti di analisi collegamenti attendibili che si applica a tutti gli utenti

Quando si dispone di protezione da minacce avanzate di Office 365 Enterprise, è necessario un criterio di collegamenti sicuro degli strumenti di analisi predefinito che si applica a tutti gli utenti nell'organizzazione. È possibile modificare i criteri in entrambi i Security &amp; centro conformità o l'interfaccia di amministrazione di Exchange. **è consigliabile utilizzare la sicurezza &amp; centro conformità per visualizzare o modificare i criteri degli strumenti di analisi**.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio**, scegliere **criteri \> ** **Collegamenti sicuri**.
    
3. Nella sezione **criteri che si applicano all'intera organizzazione** , selezionare **predefinito**e quindi fare clic su **Modifica** (pulsante Edit a forma di una matita). 
    
    ![Fare clic su Modifica per modificare il criterio predefinito per la protezione collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Nella sezione **bloccare gli URL seguenti** , specificare uno o più URL che si desidera impedire agli utenti dell'organizzazione di visitare il sito. Vedere [configurazione di un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
5. Nella sezione **impostazioni che si applicano al contenuto, ad eccezione di posta elettronica** selezionare oppure deselezionare le opzioni che si desidera utilizzare. (È consigliabile selezionare tutte le opzioni). 
    
6. Fare clic su **Salva**.
    
## <a name="add-a-policy-for-specific-email-recipients"></a>Aggiungere un criterio per i destinatari di posta elettronica specifico

Dopo aver esaminato i criteri per tutti gli utenti, è consigliabile definire ulteriori criteri per determinati gruppi di destinatari di posta elettronica. In questo modo è possibile specificare le eccezioni per il criterio predefinito. È possibile aggiungere i criteri utilizzando uno la sicurezza &amp; centro conformità (scelta consigliata) o l'interfaccia di amministrazione di Exchange. **è consigliabile utilizzare la sicurezza &amp; centro conformità per visualizzare o modificare i criteri degli strumenti di analisi**.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio**, selezionare **criterio**.
    
3. Scegliere **collegamenti sicuri**.
    
4. Nella sezione **criteri che si applicano a destinatari specifici** fare clic su **Nuovo** (pulsante nuovo simile a un segno di addizione ( **+**)).
    
    ![Selezionare nuovo per aggiungere un criterio di collegamenti sicuro per i destinatari di posta elettronica specifico](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Specificare il nome, la descrizione e le impostazioni per il criterio.
    
    **Esempio:** Per configurare un criterio non denominato "diretto clickthrough" che non consente agli utenti in un determinato gruppo all'interno dell'organizzazione a fare clic per un sito Web specifico senza protezione degli strumenti di analisi collegamenti sicuri, è possibile specificare le seguenti impostazioni consigliate: 
    
  - Nella casella **nome** non digitare alcun clickthrough diretto.
    
  - Nella casella **Descrizione** digitare una descrizione come partecipanti impedisce determinati gruppi da facendo clic su tramite di un sito Web senza verifica degli strumenti di analisi collegamenti sicuri.
    
  - Nella sezione **Selezionare l'azione** , fare clic **su**.
    
  - Selezionare **Gli allegati sicuri di utilizzo per analizzare contenuto scaricabile**.
    
  - Se questa opzione è disponibile, selezionare **Applica sicuri collegamenti ai messaggi inviati all'interno dell'organizzazione**.
    
  - Selezionare **non consentire utente fare clic su tramite URL originale**.
    
  - (È facoltativo) Nella sezione **non riscrivere gli URL seguenti** , specificare uno o più URL sono considerati attendibili per l'organizzazione. (Vedere [configurare un personalizzato elenco URL "non di riscrittura" utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - Nella sezione **Applicato a** scegliere **il destinatario è un membro del**e quindi fare clic su gruppi di cui che si desidera includere nel criterio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
6. Fare clic su **Salva**.
    
## <a name="learn-about-atp-safe-links-policy-options"></a>Informazioni sulle opzioni di criteri di collegamenti sicuro degli strumenti di analisi

Come si consente di impostare o modificare un criterio degli strumenti di analisi collegamenti sicuro, verrà visualizzato sono disponibili diverse opzioni. Nel caso in cui sono chiedendo tali opzioni, nella tabella seguente vengono descritti ciascuno di essi e degli effetti. Si noti che esistono due tipi principali di criteri per definire o modificare: un criterio predefinito che si applica a tutti gli utenti e altri criteri definiti per destinatari specifici.
  
|**Per questo criterio**|**Questa opzione**|**Produce questo risultato**|
|:-----|:-----|:-----|
|Predefinito (dopo aver definito, il criterio predefinito si applica a tutti gli utenti dell'organizzazione)  <br/> |**Bloccare gli URL seguenti** <br/> |Consente all'organizzazione di disporre di un elenco personalizzato di URL che vengono bloccati automaticamente. Quando l'utente sceglie un URL interno dell'elenco, sarà da eseguire a una [pagina di avviso](atp-safe-links-warning-pages.md) che spiega perché l'URL è bloccato.<br/> Per ulteriori informazioni, ad esempio appena aggiunto il supporto per un massimo di tre asterischi con caratteri jolly, vedere [configurazione di un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-blocked-urls-list-wtih-atp.md) (\*).  <br/> |
|Predefinita  <br/> |**Office 365 ProPlus, Office per iOS e Android** <br/> |Quando questa opzione è selezionata, degli strumenti di analisi collegamenti sicuro protezione viene applicata agli URL nei documenti presenti in Office 365 ProPlus (Word, Excel e PowerPoint in Windows o Mac OS), Office documenti aperti in iOS o dispositivi Android, 2016 di Visio in Windows e Office Online (Word Online, in linea di PowerPoint, Excel Online e OneNote Online), fornita che l'utente ha effettuato l'accesso a Office 365. <br/><br/>Se viene visualizzata solo **2016 di Office in Windows**, quindi gli aggiornamenti delle funzionalità non hanno raggiunto l'ambiente Office 365 ancora (e disponibile a breve). Nel frattempo, protezione degli strumenti di analisi collegamenti sicuro si applica a Word 2016, 2016 Excel, PowerPoint 2016 o 2016 di Visio in esecuzione su Windows.           |
|Predefinita  <br/> |**Non registrare gli utenti di fare clic sui collegamenti sicuro degli strumenti di analisi** <br/> |Quando questa opzione è selezionata, fare clic su dati per gli URL nei documenti di Word, Excel, PowerPoint e Visio non viene archiviato.  <br/> |
|Predefinita  <br/> |**Non consentire agli utenti di fare clic su tramite degli strumenti di analisi collegamenti sicuro all'URL originale** <br/> |Quando questa opzione è selezionata, gli utenti non possono procedere oltre un [messaggio di avviso](atp-safe-links-warning-pages.md) per un URL che deve essere dannoso.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**Off** <br/> |Non analizza gli URL in messaggi di posta elettronica.  <br/> Consente di definire una regola di eccezione, ad esempio una regola che non analizza gli URL in messaggi di posta elettronica per un gruppo di destinatari specifico.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**In** <br/> |Riscrittura URL agli utenti di route tramite protezione degli strumenti di analisi collegamenti sicuri quando gli utenti fare clic su URL nei messaggi di posta elettronica.  <br/> Controlla un URL quando si fa clic su un elenco di domini bloccati o dannoso URL.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**Utilizzare gli allegati sicuri per analizzare contenuto scaricabile** <br/> |Quando questa opzione è selezionata, gli URL che puntano a informazioni sul contenuto scaricabile vengono analizzati.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**Applicare sicuri collegamenti ai messaggi inviati all'interno dell'organizzazione** <br/> | Quando questa opzione è selezionata e disponibile, protezione degli strumenti di analisi collegamenti sicuro viene applicata alla posta elettronica i messaggi inviati tra utenti all'interno dell'organizzazione, fornito gli account di posta elettronica sono ospitati in Office 365.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**Non viene registrata l'utente fa clic su** <br/> |Quando questa opzione è selezionata, fare clic su dati per gli URL nella posta elettronica da mittenti esterni non vengono archiviate. Fare clic su URL il rilevamento di collegamenti nei messaggi di posta elettronica inviati all'interno dell'organizzazione non è attualmente supportato.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**Non consentire agli utenti di fare clic per URL originale** <br/> |Quando questa opzione è selezionata, gli utenti non possono procedere oltre un [messaggio di avviso](atp-safe-links-warning-pages.md) per un URL che deve essere dannoso.  <br/> |
|Un criterio creato per i destinatari di posta elettronica specifico  <br/> |**Non riscrivere gli URL seguenti** <br/> |Lascia URL quelli specificati. Consente di mantenere un elenco personalizzato di URL sicuro che non hanno bisogno di virus per un gruppo specifico di destinatari di posta elettronica nell'organizzazione.  Per ulteriori informazioni, incluse le modifiche recenti per il supporto per un carattere jolly asterisco, vedere [configurare un personalizzato elenco URL "non di riscrittura" utilizzo degli strumenti di analisi dei collegamenti sicuro](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) (\*).<br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Collegamenti degli strumenti di analisi sicuro in Office 365](atp-safe-links.md)
  
[Allegati degli strumenti di analisi sicuro in Office 365](atp-safe-attachments.md)
  
[Impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[Impostare un personalizzato elenco URL "non di riscrittura" utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)

[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

