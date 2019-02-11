---
title: Configurare i criteri di supervisione per l'organizzazione
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: Impostare criteri di supervisione revisione per acquisire le comunicazioni di dipendenti per la revisione.
ms.openlocfilehash: 898ef9951ea20dec1e0cc6c28ad1ed6f9a0ded6e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768037"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Configurare i criteri di supervisione per l'organizzazione

Utilizzare criteri di supervisione per acquisire le comunicazioni di dipendenti per un esame dai revisori interni o esterni. Per ulteriori informazioni su come criteri di supervisione consente di monitorare le comunicazioni all'interno dell'organizzazione, vedere [criteri di supervisione in Office 365](supervision-policies.md).

> [!NOTE]
> Utenti monitorati da criteri di supervisione devono disporre di una licenza di Office 365 Enterprise E3 con il componente aggiuntivo avanzate conformità o da includere in una sottoscrizione a Office 365 Enterprise E5. Se non sono un piano di E5 Enterprise esistente e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Eseguire la procedura seguente per configurare e utilizzare supervisione nella propria organizzazione Office 365:
  
- **Passaggio 1 (facoltativo)** - [Imposta gruppi per la supervisione](configure-supervision-policies.md#exampledist)

    Prima di iniziare a utilizzare supervisione, determinare che verranno loro comunicazioni rivisto e che verranno eseguite le valutazioni. Se si desidera iniziare a utilizzare solo pochi utenti per verificare il funzionamento di supervisione, è possibile ignorare l'impostazione dei gruppi per il momento.

- **Passaggio 2 (obbligatorio)** - [effettuare supervisione disponibili nell'organizzazione](configure-supervision-policies.md#MakeAvailable)

    Aggiungersi al gruppo di ruoli supervisione esaminare in modo che è possibile impostare criteri. Chiunque disponga di questo ruolo assegnato può accedere alla pagina di **supervisione** in **Dati di Governance** di & la sicurezza centro conformità. Se il messaggio di posta elettronica per la revisione è ospitato in Exchange Online, ogni revisore deve disporre anche [l'accesso a Exchange Online PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Passaggio 3 (facoltativo)** - [dizionari/dizionari personalizzati parola chiave o configurare i tipi di informazioni riservate personalizzate](configure-supervision-policies.md#sensitiveinfo)

    Se è necessario utilizzare un dizionario personalizzato parola chiave o un tipo di informazioni riservate personalizzate per i criteri di supervisione, sarà necessario creare prima di avviare la procedura guidata supervisione.

- **Passaggio 4 (obbligatorio)** - [impostare i criteri di supervisione](configure-supervision-policies.md#setupsuper)

    È necessario creare criteri di supervisione in & la sicurezza centro conformità. Questi criteri definiscono le comunicazioni sono soggetti a revisione all'interno dell'organizzazione e viene specificato che deve eseguire le revisioni. Funzioni di comunicazione comprendono posta elettronica e le comunicazioni Microsoft Teams, nonché communications piattaforma 3rd parti (ad esempio, Facebook, Twitter e così via)

- **Passaggio 5: (facoltativo)** [Test i nuovi criteri di supervisione](configure-supervision-policies.md#TestPolicy)

    Testare i criteri di supervisione per assicurarsi che funzioni nel modo desiderato è un aspetto importante di garantire che la strategia di conformità è conformi agli standard.

- **Passaggio 6 - (facoltativo)** [Configurazione di componente aggiuntivo per Outlook per i revisori che non si desidera utilizzare il dashboard di supervisione Office 365 o OWA per esaminare communications sorvegliati](configure-supervision-policies.md#UseOutlook)

    Il supervisione componente aggiuntivo per Outlook consente revisori accedere a destra supervisione funzionalità client di Outlook in modo che possano valutare e classificare ciascun elemento.

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>Passaggio 1: configurazione di gruppi per la supervisione (facoltativo)

 Quando si crea un criterio di supervisione, se ne determinerà che avranno le proprie comunicazioni esaminate e che verranno eseguite le valutazioni. Nel criterio, si utilizzerà indirizzi di posta elettronica per identificare i singoli utenti o gruppi di utenti. Per semplificare l'installazione, creare gruppi per gli utenti che dovranno le comunicazioni esaminata e per gli utenti che verranno controllare le comunicazioni. Se si sta utilizzando gruppi, potrebbe essere necessario diverse, ad esempio, se si desidera monitorare le comunicazioni tra i due gruppi distinti di persone o se si desidera specificare un gruppo a cui non è continui a essere controllati. Per informazioni dettagliate sul funzionamento, vedere [gruppi di distribuzione di esempio](configure-supervision-policies.md#GroupExample) .
  
Per controllare le comunicazioni tra o all'interno dei gruppi nell'organizzazione, impostare i gruppi di distribuzione nell'interfaccia di amministrazione di Exchange (accedere a **destinatari** \> **gruppi**). Per ulteriori informazioni sulla configurazione di gruppi di distribuzione, vedere [gestire i gruppi di distribuzione](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> È inoltre possibile utilizzare gruppi di distribuzione dinamici o gruppi di protezione per la supervisione se si preferisce. Per decidere se queste si adattino meglio l'organizzazione deve, vedere [gestire i gruppi di protezione abilitati alla posta elettronica](http://go.microsoft.com/fwlink/?LinkId=627033)e [gestire i gruppi di distribuzione dinamico](http://go.microsoft.com/fwlink/?LinkId=627058).
  
<a name="GroupExample"> </a>

### <a name="example-distribution-groups"></a>Gruppi di distribuzione di esempio

In questo esempio include un gruppo di distribuzione che è stato impostato per un'organizzazione finanziaria denominata Contoso finanziaria internazionale.
  
In Contoso Financial International, deve essere supervisionato un campionamento delle comunicazioni tra broker negli Stati Uniti. Tuttavia, i responsabili della conformità all'interno del gruppo non richiedono supervisione. In questo esempio, è possibile creare i seguenti gruppi:
  
|**Configurare il gruppo di distribuzione**|**Indirizzo del gruppo (alias)**|**Descrizione**|
|:-----|:-----|:-----|
|Tutti i broker degli Stati Uniti | US_Brokers@contoso.com | Questo gruppo include gli indirizzi di posta elettronica di tutti i broker degli Stati Uniti che lavorano per Contoso. |
| Tutti i responsabili della conformità degli Stati Uniti | US_Compliance@contoso.com  | Questo gruppo include gli indirizzi di posta elettronica per tutti i responsabili della conformità in Usa che lavorano per Contoso. Poiché questo gruppo è un sottoinsieme di tutte le Broker in USA, è possibile utilizzare l'alias per responsabili della conformità esenti dai criteri di supervisione. |
  
<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>Passaggio 2 - supervisione rende disponibili nell'organizzazione (obbligatorio)

Per rendere disponibile come opzione di menu **supervisione** in & la sicurezza centro conformità, è necessario appartenere il ruolo di amministratore di revisione supervisione.
  
A tale scopo, è possibile aggiungere familiarità con un account membro del gruppo di ruoli supervisione revisione oppure è possibile creare un nuovo gruppo di ruoli.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Aggiungere membri al gruppo di ruoli supervisione revisione

1. Accedere a [https://protection.office.com](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365.

2. In sicurezza & centro conformità, passare alle **autorizzazioni**.

3. Selezionare il gruppo di ruoli **Revisione autorità di controllo** e quindi fare clic sull'icona Modifica.

4. Nella sezione **membri** , aggiungere gli utenti che si desidera gestire supervisione per l'organizzazione.

### <a name="create-a-new-role-group"></a>Creare un nuovo gruppo di ruoli

1. Accedere a [https://protection.office.com](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365.

2. In sicurezza & centro conformità, andare a **autorizzazioni** e quindi fare clic su Aggiungi (**+**).

3. Nella sezione **ruoli** , fare clic su Aggiungi (**+**) e scorrere verso il basso per **Supervisione amministratore revisione**. Aggiungere questo ruolo al gruppo di ruoli.

4. Nella sezione **membri** , aggiungere gli utenti che si desidera gestire supervisione per l'organizzazione.

Per ulteriori informazioni sulle autorizzazioni e gruppi di ruoli, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Abilitare l'accesso PowerShell remoto per i revisori (se posta elettronica è ospitato su Exchange Online)

1. Seguire le istruzioni contenute in [abilitare o disabilitare l'accesso a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a>Passaggio 3: creare tipi di informazioni riservate personalizzate o i dizionari personalizzati parola chiave (facoltativo)

Per selezionare i tipi di informazioni riservate personalizzate esistenti o i dizionari personalizzati parola chiave della procedura guidata dei criteri di supervisione, è necessario innanzitutto creare questi elementi, se necessario.

### <a name="create-custom-sensitive-information-types"></a>Creare tipi di informazioni riservate personalizzate

1. Creare un nuovo tipo di informazioni riservate in & la protezione di Office 365 centro conformità. Passare a **classificazioni** \> **tipi di informazioni riservate** ed eseguire la procedura **guidata nuovo tipo di informazioni riservate**. Di seguito si apprenderà come:

    - Definire un nome e una descrizione per il tipo di informazioni riservate
    - Definire prossimità, livello di probabilità e gli elementi motivo principale
    - Rivedere le selezioni effettuate e creare il tipo di informazioni riservate

    Per ulteriori informazioni, vedere [creare un tipo di informazioni riservate personalizzate](create-a-custom-sensitive-information-type.md).

### <a name="create-custom-keyword-dictionarylexicon"></a>Creare una parola chiave custom dizionario/dizionario

1. Utilizzando un editor di testo (ad esempio Blocco note), creare un nuovo file che include le parole chiave che si desidera monitorare in Criteri di supervisione. Verificare che ogni termine sia su una riga separata e salvare il file in formato **Unicode/UTF-16 (Little-Endian)** .
2. Importare il file di parole chiave in tenant di Office 365 utilizzando PowerShell. Per connettersi a Office 365 PowerShell, vedere [Connect to & di sicurezza di Office 365 PowerShell centro conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Dopo la connessione a Office 365 PowerShell, eseguire i seguenti comandi per importare il dizionario di parola chiave:

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    Per ulteriori informazioni, vedere [creare un dizionario di parola chiave](create-a-keyword-dictionary.md).

3. Creare un nuovo tipo di informazioni riservate in & la protezione di Office 365 centro conformità. Passare a **classificazioni** \> **tipi di informazioni riservate** ed eseguire la procedura **guidata nuovo tipo di informazioni riservate**. Di seguito si apprenderà come:

    - Definire un nome e una descrizione per il tipo di informazioni riservate
    - Aggiungere il dizionario personalizzato come un requisito per l'elemento corrispondente
    - Rivedere le selezioni effettuate e creare il tipo di informazioni riservate

    Dopo aver creato il dizionario/dizionario personalizzato, è possibile visualizzare le parole chiave configurate utilizzando il cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) o aggiungere e rimuovere termini utilizzando il cmdlet [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) .

    Per ulteriori informazioni, vedere [creare un tipo di informazioni riservate personalizzate](create-a-custom-sensitive-information-type.md).

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>Passaggio 4: impostare i criteri di supervisione (obbligatorio)
  
1. Accedere a [https://protection.office.com](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365.

2. In sicurezza & centro conformità, selezionare **supervisione**.
  
3. Selezionare **Crea** e quindi seguire la procedura guidata per configurare le pagine seguenti del criterio. Utilizzando la procedura guidata, si apprenderà come:

    - Assegnare il criterio di un nome e descrizione.
    - Scegliere gli utenti o i gruppi della supervisione delle attività, tra cui scegliere utenti o gruppi che si desidera escludere.
    - Definire le condizioni di criteri di supervisione.
    - Scegliere se si desidera includere i tipi di informazioni riservate. Si tratta di cui è possibile selezionare tipi di informazioni riservate personalizzate e predefinite.
    - Definire la percentuale di comunicazione da esaminare.
    - Scegliere i revisori per il criterio. È possibile revisori singoli utenti o [gruppi di protezione abilitati alla posta elettronica](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).
    - Rivedere le selezioni effettuate criteri e creare il criterio.

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>Passaggio 5 - testare i criteri di supervisione (facoltativo)

Dopo aver creato un criterio di supervisione, è consigliabile eseguire il test per verificare che le condizioni definite vengono applicate correttamente dal criterio. È inoltre possibile [testare i criteri di criterio DLP perdita di dati](create-test-tune-dlp-policy.md) se i criteri di supervisione includono tipi di informazioni riservate. Eseguire la procedura seguente per verificare i criteri di supervisione:

1. Apri un client di posta elettronica o Microsoft Teams eseguito l'accesso come utente sorvegliato definito nei criteri che si desidera testare.
2. Inviare un messaggio di posta elettronica o chat Teams Microsoft che soddisfa i criteri definiti nei criteri di supervisione. Può trattarsi di una parola chiave, la dimensione degli allegati, dominio e così via. Verificare che si determinano se le impostazioni configurate condizionale del criterio è troppo restrittivo o troppo flessibile.

    > [!Note]
    > Messaggi di posta elettronica soggetti a criteri definiti vengono elaborate quasi in tempo reale e possono essere verificate immediatamente dopo aver configurato il criterio. Le chat di Microsoft Teams possono richiedere fino a 24 ore per elaborare completamente in un criterio. 

3. Accedere a Office 365 tenant come revisore designato nei criteri di supervisione. Passare a **supervisione** > *Del criterio personalizzato* > **Open** per visualizzare il report per il criterio.

<a name="UseOutlook"> </a>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a>Passaggio 6 - configurazione di componente aggiuntivo per Outlook per i revisori (facoltativo)

I revisori che si utilizza Outlook anziché utilizzare il dashboard di supervisione in Office 365 o Outlook sul web per controllare le comunicazioni è necessario installare il componente aggiuntivo di supervisione per i client di Outlook.

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Passaggio 1: Copiare l'indirizzo della cassetta postale di supervisione

Per installare il componente aggiuntivo per desktop Outlook, è necessario l'indirizzo della cassetta postale di supervisione che è stata creata come parte dell'impostazione di criteri di supervisione.
  
> [!NOTE]
> Se qualcuno altre posizioni creato il criterio, sarà necessario ottenere questo indirizzo da loro di installare il componente aggiuntivo.

 **Per trovare l'indirizzo della cassetta postale di supervisione**
  
1. Accedere al [protezione &amp; centro conformità](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365.

2. Passare alla **supervisione**.

3. Fare clic sui criteri di supervisione che sono la raccolta delle comunicazioni da controllare.

4. Nel riquadro a comparsa dettagli criterio, in **cassetta postale di supervisione**, copiare l'indirizzo.<br/>![La sezione 'Supervisione delle cassette postali' dell'elemento libero dei dettagli di criteri di supervisione che mostra l'indirizzo della cassetta postale di supervisione posti in evidenza](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>Passaggio 2: Configurare la cassetta postale di supervisione per l'accesso desktop Outlook

Successivamente, saranno necessario eseguire alcuni comandi di Exchange Online PowerShell in modo da Outlook può connettersi alla cassetta postale di supervisione revisori.
  
1. Connessione a Exchange Online PowerShell. [Come eseguire l'operazione?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. Eseguire i comandi seguenti, dove *SupervisoryReview{GUID}@domain.onmicrosoft.com* è l'indirizzo che è stato copiato nel passaggio 1 sopra e *utente* è il nome del revisore che si connettono alla cassetta postale di supervisione nel passaggio 3.

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. Attendere almeno un'ora prima di passare al passaggio 3 sotto.

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Passaggio 3: Creare un profilo di Outlook per connettersi alla cassetta postale di supervisione

Per il passaggio finale, i revisori saranno necessario creare un profilo di Outlook per connettersi alla cassetta postale di supervisione.

> [!NOTE]
> Per creare un nuovo profilo di Outlook, si utilizzerà le impostazioni di posta elettronica nel Pannello di controllo di Windows. Il percorso che è eseguire per accedere a queste impostazioni può dipendono dal sistema operativo Windows (Windows 7, Windows 8 o Windows 10) si utilizza e la versione di Outlook installata.
  
1. Aprire il pannello di controllo e nella casella di **ricerca** nella parte superiore della finestra digitare **Mail**.<br/>(Non che come ottenere il pannello di controllo? Vedere [dove è Pannello di controllo?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. Aprire l'app di **posta elettronica** .

3. In **Impostazioni di posta - Outlook**fare clic su **Mostra profili**.<br/>!['Configurazione della posta - Outlook' la finestra di dialogo con il pulsante Mostra profili posti in evidenza](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. Nella **posta elettronica**, fare clic su **Aggiungi**. Quindi, nel **Nuovo profilo**, immettere un nome per la cassetta postale supervisione (ad esempio **supervisione**).<br/>![La finestra di dialogo "Nuovo profilo" la visualizzazione del nome 'Supervisione' nella casella "Nome del profilo"](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. In **Outlook la connessione a Office 365**, fare clic su **Connetti a un account diverso**.<br/>![Il messaggio 'Outlook connettersi a Office 365' con il collegamento a "Connetti a un altro account" evidenziato](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. Nella **Configurazione automatica Account**, selezionare **installazione manuale o tipi di server aggiuntivi**e quindi fare clic su **Avanti**.

7. **Scegliere il tipo di Account**, selezionare **Office 365**. Quindi, nella casella **Indirizzo di posta elettronica** , immettere l'indirizzo della cassetta postale di supervisione che è stato copiato in precedenza.<br/>![La pagina "Scegliere il tipo di Account" della finestra di dialogo Aggiungi Account in Outlook che mostra la casella "Indirizzo di posta elettronica" evidenziata.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Quando richiesto, immettere le credenziali di Office 365.

9. Se ha esito positivo, verrà visualizzato il **supervisione - \<nome criterio\> ** cartella elencata nella visualizzazione elenco cartelle in Outlook.

## <a name="powershell-reference"></a>Guida di riferimento di PowerShell

Se necessario, è possibile creare e gestire i criteri di supervisione utilizzando i cmdlet di PowerShell seguenti:

- [Nuovo SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Set-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [Nuovo SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Set-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get-SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get-SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)