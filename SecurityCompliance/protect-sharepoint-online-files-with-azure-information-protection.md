---
title: Proteggere i file di SharePoint Online con Azure Information Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/08/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Sintesi: Applicare la protezione delle informazioni di Azure per proteggere i file in un sito del team di SharePoint Online di livello estremamente riservato.'
ms.openlocfilehash: 738e64784de20af46050413985fb7932000f864e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "28021645"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a>Proteggere i file di SharePoint Online con Azure Information Protection

 **Riepilogo:** Applicare la protezione delle informazioni di Azure per proteggere i file in un sito del team di SharePoint Online di livello estremamente riservato.
  
Utilizzare la procedura in questo articolo per configurare Azure Information Protection in modo da fornire la crittografia e le autorizzazioni per i file. Tali file possono essere aggiunti alla raccolta di SharePoint configurata per la protezione estremamente riservata. In alternativa, è possibile aprire un file direttamente dal sito e usare il client Azure Information Protection per aggiungere la crittografia. La protezione tramite crittografia e autorizzazioni si sposta insieme al file, persino quando questo viene scaricato dal sito. 

La procedura fa parte di una soluzione più ampia per configurare la protezione estremamente riservata per i siti di SharePoint e i file al loro interno. Per ulteriori informazioni, vedere [Siti e file di Secure SharePoint Online](secure-sharepoint-online-sites-and-files.md). 

L'utilizzo di Azure Information Protection per i file di SharePoint Online non è consigliato per tutti i clienti, ma è disponibile come opzione per i clienti che hanno l'esigenza di questo livello di protezione per un sottoinsieme dei file.

Alcune note importanti su questa soluzione:
- Quando la crittografia di Azure Information Protection viene applicata ai file di Office 365, il servizio non può elaborare il contenuto di tali file. Creazione condivisa, eDiscovery, ricerca, Delve e altre funzionalità di collaborazione non funzionano. I criteri di prevenzione della perdita dei dati (DLP) possono funzionare solo con i metadati (comprese le etichette di Office 365), ma non con i contenuti di tali file (ad esempio i numeri di carta di credito all'interno dei file).
- Questa soluzione richiede all'utente di selezionare un'etichetta che applica la protezione di Azure Information Protection. Se si richiede la crittografia automatica e la capacità per SharePoint di indicizzare e ispezionare i file, è consigliabile utilizzare Information Rights Management (IRM) in SharePoint Online. Quando si configura una raccolta di SharePoint per IRM, i file vengono crittografati automaticamente nel momento in cui vengono scaricati per la modifica.  IRM di SharePoint include limitazioni che potrebbero influenzare le decisioni. Per ulteriori informazioni, vedere [Configurazione di IRM nell'interfaccia di amministrazione di SharePoint](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).

## <a name="admin-setup"></a>Configurazione degli amministratori
Innanzitutto, attenersi alle istruzioni in [Attivare Azure RMS dall'interfaccia di amministrazione di Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) per la sottoscrizione di Office 365 in uso.
  
Configurare quindi Azure Information Protection con un nuovo criterio con ambito e un'etichetta secondaria per la protezione e le autorizzazioni del sito del team di SharePoint Online di livello estremamente riservato.
  
1. Accedere al portale di Office 365 con un account che dispone del ruolo Amministratore della sicurezza oppure Amministratore della società. Per informazioni, vedere [Dove accedere a Office 365 per le aziende](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. In un'altra scheda del browser, accedere al portale di Azure ([https://portal.azure.com](https://portal.azure.com)).
    
3. Se è la prima volta che viene configurato Azure Information Protection, consultare queste [istruzioni](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).

4. Nel riquadro dell'elenco, fare clic su **Ulteriori servizi**, digitare **Informazioni**, quindi fare clic su **Azure Information Protection**.

5. Fare clic su **Etichette**.
    
6. Fare clic con il pulsante destro del mouse sull'etichetta **Estremamente riservato**, quindi su **Aggiungi un'etichetta secondaria**.
    
7. Digitare un nome per l'etichetta secondaria in **Nome** e una descrizione dell'etichetta secondaria in **Descrizione**.
    
8. In **Configurare le autorizzazioni per documenti e messaggi di posta elettronica contenenti questa etichetta** fare clic su **Proteggi**.
    
9. Nella sezione **Protezione** fare clic su **Azure (chiave cloud)**.
    
10. Nel pannello **Protezione** fare clic su **Aggiungi autorizzazioni** in **Impostazioni di protezione**.
    
11. Nel pannello **Aggiungi autorizzazioni**, in **Specifica utenti e gruppi** fare clic su **Sfoglia la directory**.
    
12. Nel riquadro **Utenti e gruppi di AAD**, selezionare i membri del gruppo di accesso per il sito del team di SharePoint Online di livello estremamente riservato, quindi scegliere **Seleziona**.
    
13. In **Scegliere le autorizzazioni dal set di impostazioni o imposta personalizzato** fare clic su **Personalizza**, quindi sulla casella **Visualizza diritti**, **Modifica contenuto**, ** Salva**, **Rispondi** e **Rispondi a tutti**
    
14. Fare due volte clic su **OK**.
    
15. Nel pannello **Etichetta secondaria** fare clic su **Salva**, quindi su **OK**.

16. Nel pannello **Azure Information Protection** fare clic su **Criteri > + Aggiungi un nuovo criterio**.
    
17. Digitare un nome per il nuovo criterio in **Nome criterio** e una descrizione in **Descrizione**.
    
18. Fare clic su **Selezionare gli utenti o i gruppi a cui viene applicato il criterio > Utenti/Gruppi**, quindi selezionare i membri del gruppo di accesso per il sito del team di SharePoint Online di livello estremamente riservato.
    
19. Fare clic su **Seleziona > OK**.

20. Fare clic su **Aggiungi o rimuovi etichette**. Nel riquadro **Criteri: Aggiungere o rimuovere etichette** fare clic sul nome dell'etichetta secondaria, quindi su **OK**.   

21. Fare clic su **Salva**, quindi su **OK**.
 
## <a name="client-setup"></a>Configurazione client
A questo punto si è pronti per iniziare a creare documenti e a proteggerli con Azure Information Protection e con la nuova etichetta.
  
È necessario [installare il client Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) nel computer che esegue Windows o nel dispositivo. È possibile creare uno script e automatizzare l'installazione oppure gli utenti possono installare il client manualmente. Vedere le risorse seguenti:
  
- [Lato client di Protezione delle informazioni di Azure](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [Installazione del client di Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [Pagina di download per l'installazione manuale](https://www.microsoft.com/download/details.aspx?id=53018)
    
Dopo aver eseguito l'installazione, gli utenti eseguono il programma, quindi accedono da un'applicazione Office (ad esempio Microsoft Word) con l'account Office 365. Una nuova barra di **Information Protection** consente agli utenti di selezionare la nuova etichetta. Assicurarsi che gli utenti conoscano il sito del team di SharePoint Online e l'etichetta da usare per proteggere i file di livello estremamente riservato.
  
> [!NOTE]
> Se si dispone di più siti del team di SharePoint Online di livello estremamente riservato, è necessario creare più criteri con ambiti di Azure Information Protection con etichette secondarie con le impostazioni precedenti, con le autorizzazioni per ogni etichetta impostata per il gruppo di accesso dei membri di un sito del team di SharePoint Online specifico. 
  
## <a name="adding-permissions-for-external-users"></a>Aggiunta delle autorizzazioni per gli utenti esterni
Esistono due modi per concedere agli utenti esterni l'accesso ai file protetti con Azure Information Protection. In entrambi i casi gli utenti esterni devono avere un account Azure AD. Se gli utenti esterni non sono membri di un'organizzazione che usa Azure AD, possono ottenere un account Azure AD come utente singolo da questa pagina di iscrizione: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Per aggiungere utenti esterni a un gruppo di Azure AD utilizzato per configurare la protezione per un'etichetta, è necessario innanzitutto aggiungere l'account come utente B2B nella directory. La memorizzazione nella cache dell'[appartenenza al gruppo da parte di Azure Rights Management può richiedere alcune ore](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).  
 - Per aggiungere utenti esterni direttamente alla protezione delle etichette, è possibile aggiungere tutti gli utenti di un'organizzazione (ad esempio Fabrikam.com), un gruppo di Azure AD (ad esempio, un gruppo dell’amministrazione all'interno di un'organizzazione) o un singolo utente. Ad esempio, è possibile aggiungere un team di regolatori esterno alla protezione per un'etichetta.

## <a name="see-also"></a>Vedere anche

[Protezione di file e siti di SharePoint Online](secure-sharepoint-online-sites-and-files.md)
  
[Proteggere i siti di SharePoint Online in un ambiente di sviluppo e di testing](secure-sharepoint-online-sites-in-a-dev-test-environment.md)
  
[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni agili](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




