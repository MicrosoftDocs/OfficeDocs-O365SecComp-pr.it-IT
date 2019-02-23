---
title: Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Sintesi: applicare le etichette di Office 365 e i criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.'
ms.openlocfilehash: 759722e7e3ba7c07b869d56a271af7d40692d39e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214437"
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-dlp"></a>Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati

 **Sintesi:** applicare le etichette di Office 365 e i criteri di prevenzione della perdita dei dati ai siti del team di SharePoint Online con vari livelli di protezione delle informazioni.
  
Usare i passaggi descritti in questo articolo per progettare e implementare le etichette di Office 365 e i criteri di protezione della perdita dei dati (DLP) per i siti del team di SharePoint Online di base, riservati ed estremamente riservati. Per ulteriori informazioni su questi tre livelli di protezione, vedere [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md).
  
## <a name="how-this-works"></a>Funzionamento
1. Creare le etichette desiderate e pubblicarle. La pubblicazione può richiedere fino a 12 ore.
2. Per i siti di SharePoint desiderati, modificare le impostazioni della raccolta documenti per applicare un'etichetta agli elementi della raccolta.
3. Creare criteri di prevenzione della perdita dei dati per intervenire in base alle etichette.

Quando gli utenti aggiungono un documento alla raccolta, al documento viene assegnata un'etichetta predefinita. È possibile modificare l'etichetta, se necessario. Quando un utente condivide un documento all'esterno dell'organizzazione, i criteri di prevenzione della perdita dei dati verificano se è assegnata un'etichetta e intervengono in caso di corrispondenza all'etichetta. Quindi cercano la corrispondenza anche ad altri criteri, ad esempio la protezione dei file con i numeri di carta di credito, se questo tipo di criterio è configurato. 

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a>Etichette di Office 365 per i siti di SharePoint Online

Esistono tre fasi per creare e poi assegnare le etichette di Office 365 ai siti del team di SharePoint Online.
  
### <a name="phase-1-determine-the-office-365-label-names"></a>Fase 1: definire i nomi etichette di Office 365

In questa fase si definiscono i nomi etichette di Office 365 per i quattro livelli di protezione delle informazioni applicati ai siti del team di SharePoint Online. La tabella seguente elenca i nomi consigliati per ogni livello.
  
|**Livello di protezione del sito del team di SharePoint Online**|**Nome etichetta**|
|:-----|:-----|
|Pubblico di base  <br/> |Pubblico interno  <br/> |
|Privato di base  <br/> |Private  <br/> |
|Dati sensibili  <br/> |Dati sensibili  <br/> |
|Highly Confidential (Riservatezza elevata)  <br/> |Highly Confidential (Riservatezza elevata)  <br/> |
   
### <a name="phase-2-create-the-office-365-labels"></a>Fase 2: creare le etichette di Office 365

In questa fase si creano e poi pubblicano le etichette specificate per i diversi livelli di protezione delle informazioni.
  
Per creare le etichette, è possibile utilizzare l'interfaccia di amministrazione di Office 365 o Microsoft PowerShell.
  
### <a name="create-office-365-labels-with-the-office-365-admin-center"></a>Creare etichette di Office 365 con l'interfaccia di amministrazione di Office 365

1. Accedere al portale di Office 365 con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società. Per informazioni, vedere [Dove accedere a Office 365 per le aziende](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Dalla scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.
    
3. Dalla nuova scheda **Interfaccia di amministrazione di Office** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.
    
4. Dalla nuova scheda **Home: Sicurezza e conformità** del browser fare clic su Classificazioni > Etichette.
    
5. Nel riquadro **Home > Etichette**, fare clic sulla scheda **Conservazione** e quindi su **Crea un'etichetta**.
    
6. Nel riquadro **Denomina l'etichetta**, digitare il nome dell’etichetta e una descrizione per amministratori e utenti, quindi fare clic su **Avanti**.

7. Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.
    
8. Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.
    
9. Ripetere i passaggi da 5 a 8 per etichette aggiuntive.
    
### <a name="create-office-365-labels-with-powershell"></a>Creare etichette di Office 365 con PowerShell

1. [Connettersi al Centro sicurezza e conformità di Office 365](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409) tramite sessione remota di PowerShell e specificare le credenziali di un account con ruolo Amministratore della sicurezza o Amministratore società.
    
2. Compilare l'elenco dei nomi delle etichette ed eseguire questi comandi al prompt dei comandi di PowerShell:
    
  ```
  $labelNames=@(<list of label names, each enclosed in quotes and separated by commas>)
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
  ```

### <a name="publish-your-new-labels"></a>Pubblicare le nuove etichette

Successivamente, seguire questa procedura per pubblicare le nuove etichette di Office 365.
  
1. Dal riquadro **Home > Etichette** del Centro sicurezza e conformità, fare clic sulla scheda **Conservazione**, quindi su **Pubblica etichette**.
    
2. Nel riquadro **Scegli etichette da pubblicare**, fare clic su **Scegli etichette da pubblicare**.
    
3. Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.
    
4. Fare clic su **Fine**.
    
5. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.
    
6. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.
    
7. Nel riquadro **Denomina il criterio**, digitare un nome per il set di etichette in **Nome**, quindi fare clic su **Avanti**.
    
8. Nel riquadro **Verifica le impostazioni**, fare clic su **Pubblica etichette** e fare clic su **Chiudi**.

    
### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a>Fase 3: applicare le etichette di Office 365 ai siti di SharePoint Online

Seguire questa procedura per applicare le etichette di Office 365 alle cartelle di documenti dei siti del team di SharePoint Online.
  
1. Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **SharePoint**.
    
2. Nella nuova scheda **SharePoint** del browser selezionare un sito per cui è necessario assegnare un'etichetta di Office 365.
    
3. Nella nuova scheda del sito di SharePoint del browser fare clic su **Documenti**.
    
4. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.
    
5. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).
    
6. In **Impostazioni - Applica etichetta**, selezionare l’etichetta appropriata, quindi fare clic su **Salva**.
    
7. Chiudere la scheda per il sito di SharePoint Online.
    
8. Ripetere i passaggi da 3 a 8 per assegnare le etichette di Office 365 a siti di SharePoint Online aggiuntivi.
    
Di seguito è riportata la configurazione risultante.
  
![Etichette di Office 365 per i quattro tipi di siti del team di SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a>Criteri di prevenzione della perdita dei dati per siti di SharePoint Online

Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che notifica agli utenti la condivisione di un documento in un sito sensibile del team di SharePoint Online all'esterno dell'organizzazione.

1. Nella scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.
    
2. Nella nuova scheda **Interfaccia di amministrazione di Office** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.
    
3. Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.
    
4. Nel riquadro **Prevenzione perdita dati** fare clic su **+ Crea un criterio**.
    
5. Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.
    
5. Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello riservato in **Nome**, quindi fare clic su **Avanti**.
    
6. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.
    
7. Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.
    
8. Nel riquadro **Personalizzare i tipi di informazioni da proteggere**, fare clic su **Modifica**.
    
9. Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.
    
10. Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.
    
11. Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.
    
12. Nel riquadro **Personalizzare i tipi di informazioni da proteggere**, fare clic su **Avanti**.

13. Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).
    
14. Nel riquadro **Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica** fare clic su **Personalizza il testo del suggerimento per i criteri**.
    
15. Nella casella di testo digitare o incollare uno dei suggerimenti riportati di seguito, a seconda se è stata implementato Azure Information Protection per proteggere i file estremamente riservati:
    
  - Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.
  - I file estremamente riservati sono protetti con crittografia. Solo gli utenti esterni che hanno ricevuto le autorizzazioni per questi file dal reparto IT possono leggerli.
    
    In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.
    
16. Fare clic su **OK**.
    
17. Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, fare clic su **Avanti**.
    
18. Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.
    
19. Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.
    
Di seguito è riportata la configurazione risultante per i siti sensibili del team di SharePoint Online.
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato utilizzando l'etichetta Riservato Office 365.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
Seguire questa procedura per configurare un criterio della prevenzione della perdita dei dati che blocchi gli utenti in fase di condivisione di un documento in un sito con riservatezza elevata del team di SharePoint Online all'esterno dell'organizzazione.
  
1. Dalla scheda **Microsoft Office Home** del browser fare clic sul riquadro **Sicurezza e conformità**.
    
2. Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.
    
3. Nel riquadro **Prevenzione perdita dati** fare clic su **+ Crea un criterio**.
    
4. Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.
    
5. Nel riquadro **Denomina il criterio**, digitare il nome per il criterio DLP di livello estremamente riservato in **Nome**, quindi fare clic su **Avanti**.
    
6. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.
    
7. Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.
    
8. Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.
    
9. Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.
    
10. Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.
    
11. Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.
    
12. Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.
    
13. Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).
    
14. Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).
    
15. Nella casella di testo digitare o incollare quanto segue:
    
  - Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.
    
    In alternativa, digitare o incollare un suggerimento per i criteri che indica agli utenti come condividere un file all'esterno dell'organizzazione.
    
16. Fare clic su **OK**.
    
17. Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, fare clic su **Avanti**.
    
18. Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.
    
19. Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.
    
Di seguito è riportata la configurazione risultante per i siti con riservatezza elevata del team di SharePoint Online.
  
![Criteri di prevenzione della perdita dei dati per un sito del team di SharePoint Online isolato utilizzando l'etichetta Estremamente riservato Office 365.](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a>Passaggio successivo

[Proteggere i file di SharePoint Online con Azure Information Protection](protect-sharepoint-online-files-with-azure-information-protection.md)
    
## <a name="see-also"></a>Vedere anche

[Protezione di file e siti di SharePoint Online](secure-sharepoint-online-sites-and-files.md)
  
[Proteggere i siti di SharePoint Online in un ambiente di sviluppo e di testing](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


