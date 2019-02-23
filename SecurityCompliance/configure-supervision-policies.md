---
title: Configurare i criteri di supervisione per l'organizzazione
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Impostare un criterio di revisione di supervisione per acquisire le comunicazioni dei dipendenti per la revisione.
ms.openlocfilehash: af317194fcf551acde8c53cdf6aa38bfb040dc84
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216736"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurare i criteri di supervisione per l'organizzazione

Utilizzare i criteri di supervisione per acquisire le comunicazioni dei dipendenti per l'esame da revisori interni o esterni. Per ulteriori informazioni su come i criteri di supervisione consentono di monitorare le comunicazioni nell'organizzazione, vedere [criteri di supervisione in Office 365](supervision-policies.md).

> [!NOTE]
> Gli utenti monitorati dai criteri di supervisione devono disporre di una licenza di Office 365 Enterprise E3 con il componente aggiuntivo per la conformità avanzato o essere inclusi in un abbonamento a Office 365 Enterprise E5. Se non si dispone di un piano Enterprise E5 esistente e si vuole provare a eseguire la supervisione, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Seguire questa procedura per configurare e usare la supervisione nell'organizzazione di Office 365:
  
- **Passaggio 1 (facoltativo)** - [impostare i gruppi per la supervisione](configure-supervision-policies.md#exampledist)

    Prima di iniziare a utilizzare la supervisione, determinare gli utenti che avranno le proprie comunicazioni e che eseguiranno tali revisioni. Se si desidera iniziare a usare solo alcuni utenti per vedere come funziona la supervisione, è possibile ignorare la configurazione dei gruppi per il momento.

- **Passaggio 2 (obbligatorio)** - [rendere disponibile la supervisione nell'organizzazione](configure-supervision-policies.md#MakeAvailable)

    Aggiungersi al gruppo di ruolo revisione di superVisione per impostare i criteri. Tutti gli utenti a cui è assegnato questo ruolo **** possono accedere alla pagina di supervisione sotto la **governance dei dati** nel centro sicurezza & Compliance. Se l'indirizzo di posta elettronica da rivedere è ospitato in Exchange Online, ogni revisore deve disporre anche dell' [accesso remoto a PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Passaggio 3 (facoltativo)** - [configurare i tipi di informazioni riservate personalizzate o i dizionari/lessico delle parole chiave personalizzati](configure-supervision-policies.md#sensitiveinfo)

    Se è necessario utilizzare un tipo di informazioni riservate personalizzato o un dizionario di parole chiave personalizzato per i criteri di supervisione, è necessario crearlo prima di avviare la procedura guidata di supervisione.

- **Passaggio 4 (obbligatorio)** - [impostare un criterio di supervisione](configure-supervision-policies.md#setupsuper)

    Verranno creati i criteri di supervisione nel centro sicurezza & Compliance. Questi criteri definiscono le comunicazioni soggette a revisione nell'organizzazione e specifica gli utenti che devono eseguire le revisioni. Le comunicazioni includono la posta elettronica e le comunicazioni di Microsoft teams, nonché le comunicazioni della piattaforma di terze parti (come Facebook, Twitter e così via).

- **Passaggio 5-(facoltativo)** [Testare i nuovi criteri](configure-supervision-policies.md#TestPolicy) di supervisione

    Test dei criteri di supervisione per assicurarsi che funzioni come desiderato è una parte importante per garantire che la strategia di conformità soddisfi gli standard.

- **Passaggio 6-(facoltativo)** [Configurare il componente aggiuntivo di Outlook per i revisori che non desiderano utilizzare il dashboard di supervisione di Office 365 o Outlook sul Web (in precedenza noto come Outlook Web App) per esaminare le comunicazioni sorvegliate](configure-supervision-policies.md#UseOutlook)

    Il componente aggiuntivo di superVisione per Outlook consente ai revisori di accedere alla funzionalità di supervisione direttamente all'interno del client Outlook in modo che possano valutare e categorizzare ogni elemento.

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>Passaggio 1: configurare i gruppi per la superVisione (facoltativo)

 Quando si crea un criterio di supervisione, si determinerà gli utenti che avranno esaminato le comunicazioni e che eseguiranno tali revisioni. Nei criteri si utilizzeranno gli indirizzi di posta elettronica per identificare singoli o gruppi di persone. Per semplificare la configurazione, creare gruppi per gli utenti che avranno la propria comunicazione e i gruppi di utenti che rivedranno tali comunicazioni. Se si utilizzano i gruppi, potrebbero essere necessari diversi, ad esempio se si desidera monitorare le comunicazioni tra due gruppi distinti di persone oppure se si desidera specificare un gruppo che non verrà controllato. Per informazioni dettagliate sul funzionamento di questo metodo, vedere [gruppi di distribuzione di esempio](configure-supervision-policies.md#GroupExample) .
  
Per controllare le comunicazioni tra o all'interno di gruppi nell'organizzazione, configurare i gruppi di distribuzione nell'interfaccia di amministrazione di Exchange (andare ai **gruppi**di **destinatari** \> ). Per ulteriori informazioni sulla configurazione dei gruppi di distribuzione, vedere [Manage Distribution Groups](http://go.microsoft.com/fwlink/?LinkId=613635) .
  
> [!NOTE]
> Se si preferisce, è inoltre possibile utilizzare gruppi di distribuzione dinamici o gruppi di sicurezza per la supervisione. Per decidere se migliorare le esigenze dell'organizzazione, vedere [gestire i gruppi di sicurezza abilitaTi alla posta elettronica](http://go.microsoft.com/fwlink/?LinkId=627033)e [gestire i gruppi di distribuzione dinamici](http://go.microsoft.com/fwlink/?LinkId=627058).
  
<a name="GroupExample"> </a>

### <a name="example-distribution-groups"></a>Gruppi di distribuzione di esempio

In questo esempio viene incluso un gruppo di distribuzione che è stato configurato per un'organizzazione finanziaria denominata Contoso Financial International.
  
In Contoso Financial International, deve essere supervisionato un campionamento delle comunicazioni tra broker negli Stati Uniti. Tuttavia, i responsabili della conformità all'interno del gruppo non richiedono supervisione. In questo esempio, è possibile creare i seguenti gruppi:
  
|**Configurare il gruppo di distribuzione**|**Indirizzo del gruppo (alias)**|**Descrizione**|
|:-----|:-----|:-----|
|Tutti i broker degli Stati Uniti | US_Brokers@Contoso.com | Questo gruppo include gli indirizzi di posta elettronica di tutti i broker degli Stati Uniti che lavorano per Contoso. |
| Tutti i responsabili della conformità degli Stati Uniti | US_Compliance@Contoso.com  | Questo gruppo include gli indirizzi di posta elettronica per tutti i responsabili della conformità basati su US che lavorano per contoso. Poiché questo gruppo è un sottoinsieme di tutti i broker basati su Stati Uniti, è possibile utilizzare questo alias per esonerare i responsabili della conformità da un criterio di supervisione. |
  
<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>Passaggio 2: rendere disponibile la supervisione nell'organizzazione (obbligatorio)

Per rendere **** disponibile la supervisione come opzione di menu nel centro sicurezza & Compliance, è necessario essere assegnati al ruolo di amministratore revisione di supervisione.
  
A tale scopo, è possibile aggiungere se stessi come membro del gruppo di ruolo revisione di superVisione oppure creare un nuovo gruppo di ruoli.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Aggiungere membri al gruppo di ruoli revisione di superVisione

1. Accedere [https://protection.office.com](https://protection.office.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro sicurezza & Compliance accedere a **autorizzazioni**.

3. Selezionare il gruppo di ruoli **Revisione** di supervisione e quindi fare clic sull'icona modifica.

4. Nella sezione **membri** aggiungere gli utenti che si desidera gestire la supervisione per l'organizzazione.

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere [https://protection.office.com](https://protection.office.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro sicurezza & Compliance accedere a **autorizzazioni** e quindi fare clic su Aggiungi**+**().

3. Nella sezione **ruoli** fare clic su Aggiungi (**+**) e scorrere verso il basso fino a **amministratore Revisione**di supervisione. Aggiungere questo ruolo al gruppo di ruoli.

4. Nella sezione **membri** aggiungere gli utenti che si desidera gestire la supervisione per l'organizzazione.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere perMissions [in &amp; The Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Abilitare l'accesso remoto a PowerShell per i revisori (se la posta elettronica è ospitata su Exchange Online)

1. Seguire le istruzioni riportate in [abilitare o disabilitare l'accesso a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a>Passaggio 3: creare tipi di informazioni riservate personalizzate o dizionari per parole chiave personalizzate (facoltativo)

Per scegliere tra tipi di informazioni riservate personalizzate esistenti o dizionari di parole chiave personalizzati nella procedura guidata dei criteri di supervisione, è necessario prima di tutto creare questi elementi, se necessario.

### <a name="create-custom-sensitive-information-types"></a>Creare tipi di informazioni riservate personalizzate

1. Creare un nuovo tipo di informazioni riservate nel centro conformità di Office 365 Security &. Passare a **classificazione** \> **tipi di informazioni riservate** e seguire i passaggi descritti nella **procedura guidata nuovo tipo di informazioni riservate**. Di seguito viene indicato:

    - Definire un nome e una descrizione per il tipo di informazioni riservate
    - Definire gli elementi di prossimità, livello di confidenza e motivo primario
    - Esaminare le selezioni e creare il tipo di informazioni riservate

    Per informazioni più dettagliate, vedere [creare un tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md).

### <a name="create-custom-keyword-dictionarylexicon"></a>Creare dizionario/lessico di parole chiave personalizzato

1. Se si utilizza un editor di testo, ad esempio il blocco note, è possibile creare un nuovo file che includa i termini di parola chiave che si desidera monitorare in un criterio di supervisione. Assicurarsi che ogni termine sia su una riga distinta e salvare il file nel formato **Unicode/UTF-16 (Little endian)** .
2. Importare il file di parole chiave nel tenant di Office 365 utilizzando PowerShell. Per connettersi a Office 365 con PowerShell, vedere [Connect to office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Dopo aver effettuato la connessione a Office 365 con PowerShell, eseguire i seguenti comandi per importare il dizionario di parole chiave:

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    Per informazioni più dettagliate, vedere [creare un dizionario di parole chiave](create-a-keyword-dictionary.md).

3. Creare un nuovo tipo di informazioni riservate nel centro conformità di Office 365 Security &. Passare a **classificazione** \> **tipi di informazioni riservate** e seguire i passaggi descritti nella **procedura guidata nuovo tipo di informazioni riservate**. Di seguito viene indicato:

    - Definire un nome e una descrizione per il tipo di informazioni riservate
    - Aggiungere il dizionario personalizzato come requisito per l'elemento corrispondente
    - Esaminare le selezioni e creare il tipo di informazioni riservate

    Dopo aver creato il dizionario/lessico personalizzato, è possibile visualizzare le parole chiave configurate utilizzando il cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) oppure aggiungere e rimuovere termini utilizzando il cmdlet [set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) .

    Per informazioni più dettagliate, vedere [creare un tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md).

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>Passaggio 4: configurare un criterio di supervisione (obbligatorio)
  
1. Accedere [https://protection.office.com](https://protection.office.com) con le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Nel centro sicurezza & Compliance selezionare **supervisione**.
  
3. Selezionare **Crea** e quindi seguire la procedura guidata per impostare le pagine seguenti del criterio. Se si utilizza la procedura guidata, sarà necessario:

    - Assegnare al criterio un nome e una descrizione.
    - Scegliere gli utenti o i gruppi da controllare, inclusa la scelta degli utenti o dei gruppi che si desidera escludere.
    - Definire le condizioni dei criteri di supervisione.
    - Scegliere se si desidera includere tipi di informazioni riservate. È possibile selezionare i tipi di informazioni riservate predefinite e personalizzate.
    - Definire la percentuale di comunicazioni da esaminare.
    - Scegliere i revisori per il criterio. I revisori possono essere singoli utenti o [gruppi di sicurezza abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).
    - Esaminare le selezioni dei criteri e creare il criterio.

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>Passaggio 5-testare i criteri di supervisione (facoltativo)

Dopo aver creato un criterio di supervisione, è consigliabile verificare che le condizioni definite vengano applicate in modo corretto dal criterio. È inoltre possibile [testare i criteri di prevenzione della perdita di dati (DLP)](create-test-tune-dlp-policy.md) se i criteri di supervisione includono tipi di informazioni riservate. Attenersi alla procedura seguente per verificare i criteri di supervisione:

1. Aprire un client di posta elettronica o Microsoft teams connesso come utente controllato definito nel criterio che si desidera sottoporre a test.
2. Inviare un messaggio di posta elettronica o Microsoft teams chat che soddisfi i criteri definiti nei criteri di supervisione. Può trattarsi di una parola chiave, dimensioni degli allegati, dominio e così via. Assicurarsi di determinare se le impostazioni condizionali configurate nel criterio sono troppo restrittive o troppo indulgenti.

    > [!Note]
    > I messaggi di posta elettronica soggetti a criteri definiti vengono elaborati in tempo quasi reale e possono essere testati immediatamente dopo la configurazione del criterio. Le chat in Microsoft teams possono richiedere fino a 24 ore per il processo completo in un criterio. 

3. Accedere al tenant di Office 365 come un revisore designato nei criteri di supervisione. Passare alla **supervisione** > *del criterio* > personalizzato**aperto** per visualizzare il report per il criterio.

<a name="UseOutlook"> </a>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a>Passaggio 6: configurare il componente aggiuntivo di Outlook per i revisori (facoltativo)

I revisori che desiderano utilizzare Outlook anziché utilizzare il dashboard di superVisione in Office 365 o Outlook sul Web per esaminare le comunicazioni devono installare il componente aggiuntivo di superVisione per il client di Outlook.

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Passaggio 1: copiare l'indirizzo della cassetta postale di supervisione

Per installare il componente aggiuntivo per Outlook desktop, è necessario l'indirizzo della cassetta postale di supervisione che è stata creata come parte del programma di installazione dei criteri di supervisione.
  
> [!NOTE]
> Se un altro utente ha creato il criterio, è necessario ottenere questo indirizzo da loro per installare il componente aggiuntivo.

 **Per trovare l'indirizzo della cassetta postale di supervisione**
  
1. Accedere al [Centro sicurezza &amp; e conformità](https://protection.office.com) utilizzando le credenziali per un account di amministratore nell'organizzazione di Office 365.

2. Andare a **supervisione**.

3. Fare clic sui criteri di supervisione che raccolgono le comunicazioni che si desidera esaminare.

4. Nel riquadro a comparsa dei dettagli del criterio, in **cassetta postale**di supervisione, copiare l'indirizzo.<br/>![La sezione "cassetta postale di superVisione" del riquadro a comparsa dei dettagli del criterio di supervisione che mostra l'indirizzo della cassetta postale](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>Passaggio 2: configurare la cassetta postale di supervisione per Outlook desktop Access

Successivamente, i revisori dovranno eseguire un paio di comandi di PowerShell di Exchange online in modo che possano connettere Outlook alla cassetta postale di supervisione.
  
1. Connettersi a PowerShell di Exchange Online. [Come si esegue questa operazione?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. Eseguire i comandi seguenti, dove *SupervisoryReview {GUID} @domain. onmicrosoft.com* è l'indirizzo copiato nel passaggio 1 e l' *utente* è il nome del revisore che si collegherà alla cassetta postale di supervisione nel passaggio 3.

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. Attendere almeno un'ora prima di passare al passaggio 3 seguente.

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Passaggio 3: creare un profilo di Outlook per la connessione alla cassetta postale di supervisione

Per il passaggio finale, i revisori dovranno creare un profilo di Outlook per la connessione alla cassetta postale di supervisione.

> [!NOTE]
> Per creare un nuovo profilo di Outlook, è possibile utilizzare le impostazioni di posta elettronica nel pannello di controllo di Windows. Il percorso da eseguire per accedere a queste impostazioni può dipendere dal sistema operativo Windows (Windows 7, Windows 8 o Windows 10) in uso e dalla versione di Outlook installata.
  
1. Aprire il pannello di controllo e nella casella di **ricerca** nella parte superiore della finestra digitare **mail**.<br/>(Non si è sicuri di come accedere al pannello di controllo? Vedere [dove si trova il pannello di controllo?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. Aprire l'app di **posta elettronica** .

3. In **configurazione posta elettronica-Outlook**, fare clic su **Mostra profili**.<br/>![La finestra di dialogo "configurazione della posta elettronica-Outlook" con il pulsante ' Mostra profili ' evidenziata](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. In **posta**, fare clic su **Aggiungi**. Quindi, in **nuovo profilo**, immettere un nome per la cassetta postale di supervisione ****, ad esempio la supervisione.<br/>![La finestra di dialogo ' nuovo profilo ' che mostra il nome ' superVisione ' nella casella ' nome profilo '](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. In **Connetti Outlook a Office 365**fare clic su **Connetti a un account diverso**.<br/>![Il messaggio ' Connect Outlook to Office 365' con il collegamento ' Connetti a un account diverso ' evidenziato](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. In **Configurazione account automatico**, scegliere **installazione manuale o tipi di server aggiuntivi**, quindi fare clic su **Avanti**.

7. In **Scegli il tipo di account**, scegli **Office 365**. Nella casella indirizzo di **posta elettronica** immettere quindi l'indirizzo della cassetta postale di supervisione copiata in precedenza.<br/>![La pagina ' Scegli il tipo di account ' della finestra di dialogo ' Aggiungi account ' in Outlook che mostra la casella ' indirizzo di posta elettronica ' evidenziata.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Quando richiesto, immettere le credenziali di Office 365.

9. In caso di esito positivo, verrà visualizzata la cartella del **nome \<\> del criterio** di supervisione elencata nella visualizzazione elenco cartelle in Outlook.

## <a name="powershell-reference"></a>Informazioni di riferimento su PowerShell

Se necessario, è possibile creare e gestire i criteri di supervisione utilizzando i cmdlet di PowerShell seguenti:

- [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get-SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get-SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)