---
title: Configurare i criteri dei collegamenti sicuri ATP di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection: M365-security-compliance
description: Impostare i criteri collegamenti sicuri per proteggere l'organizzazione da collegamenti dannosi nei file di Word, Excel, PowerPoint e Visio, nonché nei messaggi di posta elettronica.
ms.openlocfilehash: ee60b8fa5824b5e7ff478370216b52d17a6dc94f
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123957"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Configurare i criteri dei collegamenti sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è destinato ai clienti aziendali. Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

I [collegamenti sicuri di ATP](atp-safe-links.md), una funzionalità di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), consentono di proteggere l'organizzazione da collegamenti dannosi utilizzati per il phishing e altri attacchi. Se si dispone delle [autorizzazioni necessarie per il Centro sicurezza &amp; e conformità di Office 365](permissions-in-the-security-and-compliance-center.md), è possibile configurare i criteri dei collegamenti sicuri di ATP per garantire che, quando gli utenti fanno clic su indirizzi Web (URL), l'organizzazione sia protetta. I criteri dei collegamenti sicuri di ATP possono essere configurati per analizzare gli URL nella posta elettronica e negli URL nei documenti di Office.
  
Le [nuove funzionalità vengono continuamente aggiunte al trifosfato di adenosina](office-365-atp.md#new-features-in-office-365-atp). Man mano che si aggiungono nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri dei collegamenti sicuri ATP esistenti.

## <a name="what-to-do"></a>cosa fare 
  
1. [Esaminare i prerequisiti](#review-the-prerequisites).
    
2. [Rivedere e modificare il criterio dei collegamenti sicuri ATP predefinito che si applica a tutti gli utenti](#define-an-atp-safe-links-policy-that-applies-to-everyone). Ad esempio, è possibile [configurare l'elenco degli URL bloccati personalizzati per i collegamenti sicuri di ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Aggiungere o modificare i criteri per i destinatari di messaggi di posta elettronica specifici](#add-a-policy-for-specific-email-recipients), inclusa [la configurazione dell'elenco di URL personalizzati "non riscrivere" per i collegamenti sicuri di ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. Informazioni [sulle opzioni dei criteri collegamenti sicuri di ATP](#learn-about-atp-safe-links-policy-options) (in questo articolo), incluse le impostazioni per le modifiche recenti.
    
## <a name="step-1-review-the-prerequisites"></a>Passaggio 1: esaminare i prerequisiti

- Assicurarsi che l'organizzazione disponga di [Office 365 Advanced Threat Protection](office-365-atp.md).
    
- Verificare di disporre delle autorizzazioni necessarie. Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente: <br>

    |Ruolo  |Dove/come assegnato  |
    |---------|---------|
    |Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
    |Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
    |Gestione dell'organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

    Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Verificare che i client di Office siano configurati per l'utilizzo dell' [autenticazione moderna](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (per la protezione dei collegamenti sicuri di ATP nei documenti di Office).
    
- Informazioni [sulle opzioni dei criteri collegamenti sicuri di ATP](#learn-about-atp-safe-links-policy-options) (in questo articolo). 

- Consentono fino a 30 minuti affinché il criterio nuovo o aggiornato venga esteso a tutti i datacenter di Office 365.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Passaggio 2: definire (o rivedere) il criterio dei collegamenti sicuri ATP che si applica a tutti

Quando si dispone di [Office 365 Advanced Threat Protection](office-365-atp.md), si avrà un criterio di collegamenti sicuri ATP predefinito che si applica a tutti gli utenti dell'organizzazione. Assicurarsi di esaminare e, se necessario, modificare il criterio predefinito.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione. 
    
2. Nella barra di spostamento a sinistra, in **gestione minacce**, scegliere **collegamenti sicuri**per i ** \> criteri** .
    
3. Nei **criteri che si applicano all'intera sezione organizzazione** selezionare **predefinita**e quindi fare clic su **modifica** (il pulsante modifica è simile a una matita).<br/>![Fare clic su modifica per modificare il criterio predefinito per la protezione dei collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Nella sezione **blocca gli URL seguenti** specificare uno o più URL che si desidera impedire agli utenti dell'organizzazione di visitare. Per ulteriori informazioni, vedere [configurare un elenco di URL bloccati personalizzato utilizzando collegamenti sicuri di ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
5. Nelle **impostazioni che si applicano al contenuto, ad eccezione della sezione posta elettronica** , selezionare (o deselezionare) le opzioni che si desidera utilizzare. (Si consiglia di selezionare tutte le opzioni). 
    
6. Scegliere **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Passaggio 3: aggiungere o modificare i criteri per i collegamenti sicuri di ATP che si applicano ai destinatari di messaggi di posta elettronica specifici

Dopo aver esaminato (o modificato) il criterio collegamenti sicuri ATP predefinito che si applica a tutti gli utenti, il passaggio successivo consiste nel definire criteri aggiuntivi che si applicano a destinatari specifici. Ad esempio, è possibile specificare eccezioni per il criterio predefinito definendo un criterio aggiuntivo. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione. 
    
2. Nella barra di spostamento sinistra fare clic su **criteri**in **gestione minacce**.
    
3. Scegliere **collegamenti attendibili**.
    
4. Nella sezione **criteri che si applicano a destinatari specifici** scegliere **nuovo** (il nuovo pulsante è simile a un segno di addizione ( **+**)).<br/>![Scegliere nuovo per aggiungere un criterio per i collegamenti sicuri per i destinatari di posta elettronica specifici](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Specificare il nome, la descrizione e le impostazioni per il criterio.<br/>**Esempio:** Per impostare un criterio denominato "nessun clic diretto tramite" che non consenta agli utenti di un determinato gruppo dell'organizzazione di fare clic su un sito Web specifico senza protezione di collegamenti sicuri ATP, è possibile specificare le impostazioni consigliate seguenti: 
    
  - Nella casella **nome** digitare nessun clic diretto.
    
  - Nella casella **Descrizione** Digitare una descrizione analoga, consente di impedire agli utenti di alcuni gruppi di fare clic su un sito Web senza verifica dei collegamenti sicuri di ATP.
    
  - Nella sezione **selezionare l'azione** scegliere attivato. ****
    
  - Selezionare **USA allegati sicuri per analizzare il contenuto scaricabile**.
    
  - Se questa opzione è disponibile, selezionare **applica collegamenti sicuri ai messaggi inviati all'interno dell'organizzazione**.
    
  - Selezionare non **consentire all'utente di fare clic sull'URL originale**.
    
  - (Facoltativo) Nella sezione non **riscrivere gli URL seguenti** specificare uno o più URL considerati attendibili per l'organizzazione. (Vedere [configurare un elenco di URL "non riscrivere" personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - Nella sezione **applicato a** , scegliere **il destinatario è un membro di**, quindi scegliere il gruppo o i gruppi che si desidera includere nel criterio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
6. Scegliere **Save**.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Passaggio 4: informazioni sulle opzioni dei criteri collegamenti sicuri di ATP

Quando si configurano o si modificano i criteri dei collegamenti sicuri di ATP, saranno disponibili diverse opzioni. Nel caso in cui si stiano chiedendo quali sono queste opzioni, nella tabella seguente vengono descritte le caratteristiche di ciascuna di esse. Tenere presente che sono disponibili due tipi principali di criteri dei collegamenti sicuri ATP da definire o modificare:
- un [criterio predefinito](#default-policy-options) che si applica a tutti 
- [criteri aggiuntivi definiti per destinatari specifici](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Opzioni predefinite per i criteri

Le opzioni dei criteri predefinite si applicano a tutti gli utenti dell'organizzazione.

|Questa opzione  |Produce questo risultato  |
|---------|---------|
| **Blocca gli URL seguenti** <br/>    | Consente all'organizzazione di disporre di un elenco personalizzato di URL che vengono bloccati automaticamente. Quando gli utenti fanno clic su un URL in questo elenco, verranno indirizzati a una [pagina di avviso](atp-safe-links-warning-pages.md) che spiega perché l'URL è bloccato.<br/> Per ulteriori informazioni, vedere [configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP      |
| **Office 365 ProPlus, Office per iOS e Android** <br/>    | Quando questa opzione è selezionata, la protezione dei collegamenti sicuri di ATP viene applicata agli URL nei documenti aperti in Office 365 ProPlus (Word, Excel e PowerPoint in Windows o Mac OS), nei documenti di Office su iOS o nei dispositivi Android, in Visio 2016 su Windows e in Office Online (Word Online, PowerPoint online, Excel online e OneNote online), a condizione che l'utente abbia eseguito l'accesso a Office 365. <br/><br/>Se si vede solo **office 2016 su Windows**, gli aggiornamenti delle funzionalità non hanno ancora raggiunto l'ambiente Office 365 (e verranno presto). Fino ad allora, la protezione per i collegamenti sicuri di ATP si applica a Word 2016, Excel 2016, PowerPoint 2016 o Visio 2016 in esecuzione su Windows.            |
| **Non monitorare quando gli utenti fanno clic su collegamenti sicuri di ATP** <br/>  | Quando questa opzione è selezionata, fare clic su dati per gli URL in Word, Excel, PowerPoint e documenti di Visio non archiviati.  <br/> |
|**Non consentire agli utenti di fare clic su collegamenti sicuri ATP all'URL originale** <br/> |Quando questa opzione è selezionata, gli utenti non possono continuare a passare una [pagina di avviso](atp-safe-links-warning-pages.md) a un URL determinato come dannoso.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Criteri che si applicano ai destinatari di posta elettronica specifici

|Questa opzione  |Produce questo risultato  |
|---------|---------|
|**Off** <br/> |Non analizza gli URL nei messaggi di posta elettronica.  <br/> Consente di definire una regola di eccezione, ad esempio una regola che non analizza gli URL nei messaggi di posta elettronica per uno specifico gruppo di destinatari.  <br/> |
|**Nella** <br/> |Riscrive gli URL per instradare gli utenti tramite la protezione dei collegamenti sicuri ATP quando gli utenti fanno clic su URL nei messaggi di posta elettronica.  <br/> Verifica un URL quando si fa clic su un elenco di URL bloccati o dannosi.  <br/> |
|**Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile** <br/> |Quando questa opzione è selezionata, gli URL che puntano al contenuto scaricabile vengono analizzati.  <br/> |
|**Applicazione di collegamenti sicuri ai messaggi inviati all'interno dell'organizzazione** <br/> | Quando questa opzione è disponibile e selezionata, la protezione dei collegamenti sicuri di ATP viene applicata ai messaggi di posta elettronica inviati tra gli utenti dell'organizzazione, purché gli account di posta elettronica siano ospitati in Office 365.  <br/> |
|**Non monitorare i clic dell'utente** <br/> |Quando questa opzione è selezionata, fare clic su dati per gli URL in messaggi di posta elettronica da mittenti esterni non archiviati. URL fare clic su rilevamento per i collegamenti all'interno dei messaggi di posta elettronica inviati all'interno dell'organizzazione non è attualmente supportato.  <br/> |
|**Non consentire agli utenti di fare clic sull'URL originale** <br/> |Quando questa opzione è selezionata, gli utenti non possono continuare a passare una [pagina di avviso](atp-safe-links-warning-pages.md) a un URL determinato come dannoso.  <br/> |
|**Non riscrivere gli URL seguenti** <br/> |Lascia gli URL così come sono. Mantiene un elenco personalizzato di URL sicuri che non devono essere analizzati per uno specifico gruppo di destinatari di posta elettronica nell'organizzazione.  Per ulteriori informazioni, vedere [configurare un elenco di URL "non riscrivere" personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) , incluse le modifiche recenti al supporto per gli\*asterischi con caratteri jolly ().<br/> |
   
## <a name="next-steps"></a>Passaggi successivi

Una volta che i criteri per i collegamenti sicuri di ATP sono sul posto, è possibile vedere in che modo ATP è in funzione per il orgnization visualizzando i report. Per ulteriori informazioni, vedere le risorse seguenti:

- [Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Utilizzo di Esplora risorse nel &amp; Centro sicurezza e conformità](use-explorer-in-security-and-compliance.md)

Rimanere in cima a nuove funzionalità che vengono a ATP. visitare la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e conoscere le [nuove funzionalità che vengono aggiunte a ATP](office-365-atp.md#new-features-in-office-365-atp).