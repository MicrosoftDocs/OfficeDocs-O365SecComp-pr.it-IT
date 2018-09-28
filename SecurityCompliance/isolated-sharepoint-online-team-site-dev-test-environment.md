---
title: Sito del team di SharePoint Online isolato nell’ambiente di sviluppo/test
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: "Riepilogo: Configurare un sito del team SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo e di testing di Office 365."
ms.openlocfilehash: 0aa5e6e47344134b1e103fb287f627afd2808af6
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345818"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Sito del team di SharePoint Online isolato nell’ambiente di sviluppo/test

 **Riepilogo:** Configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo e di testing di Office 365.
  
SharePoint Online siti dei team in Office 365 sono percorsi per la collaborazione con una raccolta documenti comuni, un blocco appunti di OneNote e altri servizi. In molti casi, si desidera ampio accesso e la collaborazione tra organizzazioni o reparti. In alcuni casi, tuttavia, si desidera controllare rigidamente l'accesso e le autorizzazioni per la collaborazione tra un piccolo gruppo di utenti.
  
Accesso ai siti dei team di SharePoint Online e operazioni eseguibili dagli utenti è controllato dai livelli di autorizzazione e gruppi di SharePoint. Per impostazione predefinita, i siti di SharePoint Online sono tre livelli di accesso:
  
- **Membri**, che possono visualizzare, creare e modificare le risorse sul sito.
    
- **Proprietari**, che hanno il controllo completo del sito, compresa la possibilità di modificare le autorizzazioni.
    
- **Visitatori**, che possono solo visualizzare le risorse sul sito.
    
In questo articolo passaggi è la configurazione di un sito del team di SharePoint Online isolato per un progetto di ricerca segreta denominato ProjectX. I requisiti di accesso sono:
  
- Solo i membri del progetto possono accedere al sito e ai suoi contenuti (documenti, Blocco appunti di OneNote, Pages), con livelli di autorizzazione di SharePoint per la modifica e la visualizzazione controllati mediante l'appartenenza al gruppo.
    
- Solo l'autore del sito e i membri di un gruppo Amministratori per il sito possono eseguire operazioni amministrative sul sito, inclusa la modifica delle autorizzazioni a livello del sito.
    
Esistono tre fasi per configurare un sito del team di SharePoint Online isolato nell'ambiente di sviluppo e di testing di Office 365:
  
1. Creare l'ambiente di sviluppo/testing di Office 365
    
2. Creare gli utenti e i gruppi per ProjectX.
    
3. Creare un nuovo sito del team ProjectX SharePoint Online e il relativo isolamento.
    
> [!TIP]
> Fare clic [qui](http://aka.ms/catlgstack) per consultare una mappa di tutti gli articoli relativi alla guida del laboratorio di testing cloud di One Microsoft.
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a>Fase 1: creare l'ambiente di sviluppo/test di Office 365 aziendale leggero o simulato

Se si desidera creare un sito del team di SharePoint Online isolato in un modo semplice con i requisiti minimi, seguire le istruzioni in fasi 2 e 3 [dell'ambiente di sviluppo e di testing di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).
  
Se si desidera creare un sito del team di SharePoint Online isolato in una configurazione enterprise simulato, seguire le istruzioni in [DirSync per l'ambiente di sviluppo e di testing di Office 365](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).
  
> [!NOTE]
> La creazione di un sito di SharePoint Online isolato non richiede l'ambiente di sviluppo/test aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Windows Server AD. Qui viene fornito come un'opzione in modo da poter testare un sito di SharePoint Online isolato e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: Creare gli account utente e accedere ai gruppi

Utilizzare le istruzioni riportate in [connessione a Office 365 PowerShell](https://technet.microsoft.com/library/dn975125.aspx) per connettersi alla sottoscrizione Office 365 trail con l'account di amministratore globale di:
  
- Dal computer (per l'ambiente di sviluppo/test di Office 365 leggero).
    
- Dalla macchina virtuale CLIENT1 (per l'ambiente di sviluppo/test di Office 365 aziendale simulato).
    
Per creare nuovi gruppi di accesso per il sito del team ProjectX SharePoint Online, eseguire questi comandi dal prompt dei comandi di Windows Azure Active Directory Module per Windows PowerShell:
  
```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

> [!TIP]
> Fare clic [qui](https://gallery.technet.microsoft.com/PowerShell-commands-for-an-b2608df1) per un file di testo che contiene tutti i comandi di PowerShell in questo articolo.
  
Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri e quindi eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:
  
```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser**, prendere nota della password generata per l'account Lead Designer e conservarla in una posizione sicura.
  
Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:
  
```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser**, prendere nota della password generata per l'account Lead Researcher e conservarla in una posizione sicura.
  
Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:
  
```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser**, prendere nota della password generata per l'account Development VP e conservarla in una posizione sicura.
  
Successivamente, per aggiungere i nuovi account per i nuovi gruppi di accesso, eseguire questi comandi di PowerShell dal prompt dei comandi di Windows Azure Active Directory Module per Windows PowerShell:
  
```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Risultati:
  
- Il gruppo di accesso ProjectX membri contiene gli account utente di coordinare Designer e coordinare Organizzatore ricerche
    
- Il gruppo di accesso ProjectX Admins contiene l'account amministratore globale per la sottoscrizione di prova
    
- Il gruppo di accesso ProjectX visualizzatori contiene l'account utente di sviluppo Vicepresidente
    
Nella figura 1 vengono illustrati i gruppi di accesso e la propria appartenenza.
  
**Figura 1**

![Gruppi di Office 365 e appartenenza a un sito di gruppi di SharePoint Online isolato](media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)
  
## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Creare un nuovo sito del team ProjectX SharePoint Online e isolare l'attacco

Per creare un sito del team di SharePoint Online per ProjectX, eseguire le operazioni seguenti:
  
1. Utilizzando un browser in uno nel computer locale (configurazione semplificata) o su CLIENT1 (configurazione aziendale simulato), accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando l'account amministratore globale.
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella nuova scheda SharePoint del browser fare clic su + **Crea sito**.
    
4. **Nome del sito del Team**, digitare **ProjectX**. **Le impostazioni di Privacy**, selezionare **privato: solo membri possono accedere al sito**.
    
5. In **Descrizione sito del team**, digitare **Sito di SharePoint per ProjectX**, quindi fare clic su **Avanti**.
    
6. In **cui si desidera aggiungere**? riquadro, fare clic su **Fine**.
    
7. Nella nuova scheda **ProjectX-Home** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.
    
8. Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).
    
9. Nella nuova scheda **Autorizzazioni: ProjectX** visualizzata nel browser, fare clic su **Impostazioni richieste di accesso**.
    
10. Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti richieste di accesso** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.
    
11. Fare clic su **Membri ProjectX** nell'elenco.
    
12. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.
    
13. Nella finestra di dialogo **Condividi**, digitare **ProjectX-Members**, selezionarlo e quindi fare clic su **Condividi**.
    
14. Fare clic sul pulsante Indietro del browser.
    
15. Fare clic su **Proprietari ProjectX** nell'elenco.
    
16. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.
    
17. Nella finestra di dialogo **Condividi**, digitare **ProjectX-Admins**, selezionarlo e quindi fare clic su **Condividi**.
    
18. Fare clic sul pulsante Indietro del browser.
    
19. Fare clic su **Visitatori ProjectX** nell'elenco.
    
20. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.
    
21. Nella finestra di dialogo **Condividi**, digitare **ProjectX-Viewers**, selezionarlo e quindi fare clic su **Condividi**.
    
22. Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **ProjectX-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.

    
Ecco i risultati della configurazione delle autorizzazioni:
  
- Il gruppo di SharePoint membri ProjectX contiene solo il gruppo di accesso ProjectX membri (che include solo gli account utente provocare Designer e coordinare ricercatori) e del gruppo ProjectX (che contiene solo l'account utente amministratore globale).
    
- Gruppo di SharePoint proprietari ProjectX contiene solo il gruppo di accesso ProjectX Admins (che contiene solo l'account utente amministratore globale).
    
- Il gruppo di SharePoint visitatori ProjectX contiene solo i visualizzatori ProjectX gruppo di accesso (che contiene solo l'account utente di sviluppo Vicepresidente).
    
- I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo ProjectX-Admins).
    
- Altri account utente non possono accedere al sito e alle relative risorse o richiedere l'accesso al sito.
    
Nella figura 2 vengono mostrati i gruppi di SharePoint e la relativa appartenenza.
  
**Figura 2**

![Gruppi di SharePoint Online e appartenenza a un sito di gruppi di SharePoint Online isolato](media/595abff4-64f9-49de-a37a-c70c6856936b.png)
  
A questo punto possiamo illustrare l'accesso utilizzando l'account utente di coordinare Designer:
  
1. Chiudere la scheda **ProjectX-Home** visualizzata nel browser, quindi fare clic sulla scheda **Microsoft Office Home** nel browser.
    
2. Fare clic sul nome dell'amministratore globale e quindi fare clic su **Disconnetti**.
    
3. Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando il nome dell'account coordinare progettazione e la relativa password.
    
4. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
5. Nella scheda **SharePoint** nuovo nel browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic su sito del team **ProjectX** . Una nuova scheda verrà visualizzato nel browser per il sito del team ProjectX.
    
6. Fare clic sull'icona delle impostazioni. Si noti che non sono presenti opzioni per **Autorizzazioni sito**. È corretto perché solo i membri del gruppo ProjectX-Admins possono modificare le autorizzazioni sul sito
    
7. Aprire il Blocco note o un editor di testo di propria scelta.
    
8. Copiare l'URL del sito del team ProjectX e incollarlo in una nuova riga nel blocco note o l'editor di testo.
    
9. Nella nuova scheda **ProjectX-Home** visualizzata nel browser, fare clic su **Documenti**.
    
10. Copiare l'URL della cartella dei documenti di ProjectX e incollarlo su una nuova riga nel Blocco note o nell'editor di testo.
    
11. Nella nuova scheda **ProjectX-Documents** visualizzata nel browser, fare clic su **Nuovo > Documento Word**.
    
12. Digitare del testo nella pagina **Word Online**, attendere che lo stato riporti **Salvato**, fare clic sul pulsante Indietro nel browser, quindi aggiornare la pagina. Viene visualizzato un nuovo file **Document.docx** nella cartella **Documenti**.
    
13. Fare clic sui puntini di sospensione del documento **Document.docx**, quindi fare clic su **Ottieni un collegamento**.
    
14. Copiare l'URL della finestra di dialogo **Condividi 'Document.docx'** e incollarlo in una nuova riga nel blocco note o l'editor di testo e quindi chiudere la finestra di dialogo **Condividi 'Document.docx'** .
    
15. Chiudere le schede **ProjectX-Documents** e **SharePoint** nel browser, quindi fare clic sulla scheda **Microsoft Office Home**.
    
16. Fare clic sul nome **Lead Designer**, quindi su **Disconnetti**.

    
A questo punto possiamo illustrare l'accesso utilizzando l'account utente Vicepresidente dello sviluppo:
  
1. Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando il nome dell'account Vicepresidente di sviluppo e la relativa password.
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella scheda **SharePoint** nuovo nel browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic su sito del team **ProjectX** . Una nuova scheda verrà visualizzato nel browser per il sito del team ProjectX.
    
4. Fare clic su **Documenti**, quindi sul file **Document.docx**.
    
5. Nella scheda **Document.docx** nel browser, provare a modificare il testo. Viene visualizzato il messaggio **Documento di sola lettura.** Infatti, l'account utente Development VP può solo visualizzare le autorizzazioni per il sito.
    
6. Chiudere le schede **Document.docx**, **ProjectX-Documents** e **SharePoint** nel browser.
    
7. Fare clic sulla scheda **Microsoft Office Home**, selezionare il nome **Development VP** e quindi fare clic su **Disconnetti**.

    
A questo punto possiamo illustrare l'accesso con un account utente che non dispone delle autorizzazioni:
  
1. Accedere al portale di Office 365 ([https://portal.office.com](https://portal.office.com)) utilizzando il nome dell'account utente 3 e la relativa password.
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. 	Nella nuova scheda **SharePoint** nel browser, digitare **ProjectX** nella casella di ricerca e quindi attivare la ricerca. Viene visualizzato il messaggio **Nessun elemento corrispondente alla ricerca.**
    
4. Dall'istanza aperta del Blocco note o dell'editor di testo, copiare l'URL per il sito di ProjectX nella barra degli indirizzi del browser e premere **Invio**. Viene visualizzata una pagina **Accesso negato**.
    
5. Dal Blocco note o dall'editor di testo, copiare l'URL per la cartella dei documenti di ProjectX nella barra degli indirizzi del browser e premere **Invio**. Viene visualizzata una pagina **Accesso negato**.
    
6. Dal Blocco note o dall'editor di testo, copiare l'URL per il file Documents.docx nella barra degli indirizzi del browser e premere **Invio**. Viene visualizzata una pagina **Accesso negato**.
    
7. Chiudere la scheda **SharePoint** nel browser, fare clic sulla scheda **Microsoft Office Home**, fare clic sul nome **User 3** e quindi su **Disconnetti**.

    
Nel sito di SharePoint Online isolato è pronto per le operazioni aggiuntive.
  
## <a name="next-step"></a>Passaggio successivo

Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)
  
[Test Lab Guide (TLG) di adozione cloud](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[Ambiente di sviluppo/test della configurazione di base](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)
  
[Ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)
  
[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




