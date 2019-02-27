---
title: Aggiungere i depositari a un caso avanzato di eDiscovery (anteprima)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 730e1fe40756bcb38f3b071137828072f4e2dcb5
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296719"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>Aggiungere i depositari a un caso avanzato di eDiscovery (anteprima)

Utilizzando Advanced eDiscovery (Preview), è possibile sfruttare lo strumento di gestione del custode incorporato per coordinare i flussi di lavoro in merito alla gestione dei depositari e identificare le origini dati rilevanti e detentive all'interno di un caso. Quando si aggiunge un custode, il sistema è in grado di identificare automaticamente e inserire le esenzioni nella cassetta postale di Exchange principale e nel sito di OneDrive for business. Quando si esegue l'individuazione, è possibile anche scoprire e mappare altre cassette postali o siti a cui è stato effettuato l'accesso di un custode nel passato o i team a cui è membro un custode.

Utilizzare il flusso di lavoro seguente per aggiungere e gestire i depositari nei casi avanzati di eDiscovery (Preview) all'interno del Centro sicurezza & Compliance. 

![Scheda Gestione depositaria](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a>Passaggio 1: identificare i potenziali depositari

Il primo passaggio consiste nell'identificare i depositari idonei per la propria materia. Per aggiungere depositari a un caso, è necessario essere membri del gruppo di ruoli eDiscovery managers o eDiscovery Admins.   

![Identificare i potenziali depositari](../media/AddCustodianStep1.png)

Per aggiungere i depositari a un caso avanzato esistente di eDiscovery (anteprima):

1. Dalla pagina **Advanced eDiscovery (Preview)** , passare al caso.
 
2. Dopo aver selezionato un caso, passare alla scheda **depositari** e fare clic su **+ Aggiungi custode**. 
 
3. Scegliere i depositari che si desidera aggiungere al caso. È possibile iniziare digitando la ricerca e selezionando gli utenti dall'Azure Active Directory dell'organizzazione.
 
4. Dopo aver completato l'elenco dei depositari, fare clic su **Avanti** per iniziare a identificare potenziali origini dati. 
  
## <a name="optional-step-2-select-custodian-data-sources"></a>Optional Passaggio 2: selezionare origini dati di un custode

Dopo aver aggiunto i depositari a un caso, è possibile sfruttare Office 365 per identificare e preservare le origini dati del custode principale. Il passaggio successivo in questo flusso di lavoro consiste nel selezionare le origini dati di proprietà dei depositari specificati nel passaggio 1. 

![Selezionare origini dati di custodia](../media/AddCustodianStep2.png)

Per identificare le origini dati del custode: 

1. Per ogni custode, selezionare **Exchange** se si desidera che il sistema identifichi automaticamente e aggiunga la cassetta postale di Exchange principale del custode. 
 
2. Per ogni custode, selezionare **OneDrive** se si desidera che il sistema identifichi automaticamente e aggiunga l'URL di OneDrive primario del custode. 

    Dopo aver apportato le selezioni, il sistema tenterà automaticamente di identificare le origini dati e di aggiungerle al caso.
 
4. Fare clic su **Avanti** per iniziare a mappare le origini dati aggiuntive al custode.

## <a name="optional-step-3-map-additional-data-sources"></a>Optional Passaggio 3: mappare origini dati aggiuntive

A seconda del caso, è possibile aggiungere anche cassette postali che un determinato custode può aver utilizzato in passato, gruppi in cui un custode è attualmente membro o siti a cui un custode ha avuto accesso in passato. Oltre alle origini dati del custode principale, è possibile aggiungere altre origini dati di Office 365 a un custode o sfruttare Office 365 per identificare anche le origini dati potenzialmente rilevanti. 

![Mapping di origini dati aggiuntive](../media/AddCustodianStep3.PNG)

Per eseguire il mapping di cassette postali, siti o team a un determinato custode:

1. Selezionare **Aggiorna** per assegnare le posizioni di contenuto, come le cassette postali, i siti e i team a un determinato custode. 

2. Nel riquadro a comparsa, specificare quanto segue:
   
    -  **Cassette postali di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** . Per specificare le cassette postali da assegnare al custode selezionato, utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione. È inoltre possibile assegnare la cassetta postale associata a un gruppo di Office 365 o a un team Microsoft. Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.

        > [!NOTE]
        > Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, lo strumento di selezione delle cassette postali visualizzato è vuoto. Questo è un progetto che consente di migliorare le prestazioni. Per aggiungere persone a questo elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca.
     
     - **Siti di SharePoint** -fare clic su **Choose sites** , quindi fare clic su choose **sites** again per specificare altri siti di SharePoint e OneDrive for business che si desidera assegnare al custode selezionato. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Office 365 o un team di Microsoft. Digitare l'URL per ogni sito che si desidera assegnare. Fare clic su **Scegli**e quindi su **fine**.
     - **Microsoft teams** -fare clic su **Scegli team** e quindi fare di nuovo clic su **Scegli squadre** per visualizzare un elenco di gruppi di team Microsoft che il custode è un membro di oggi. Selezionare i team che si desidera aggiungere al custode. Una volta selezionata, il sistema identificherà automaticamente & selezionare il sito di SharePoint associato e la cassetta postale del gruppo associata a quel team Microsoft. Fare clic su **Scegli**e quindi su **fine**.
        
      > [!NOTE]
      > Per aggiungere ulteriori Microsoft teams, sarà necessario aggiungere separatamente la cassetta postale e il sito di SharePoint come illustrato in alto.

Dopo aver completato la mappatura delle origini, è possibile visualizzare le cassette postali, i siti e i team totali per i depositari appena aggiunti. Dopo aver finalizzato le origini dati rilevanti per uno specifico custode, questo mapping verrà mantenuto e esteso all'insieme eDiscovery, all'elaborazione e alla revisione dei flussi di lavoro. 

## <a name="optional-step-4-place-custodians-on-hold"></a>Optional Passaggio 4: mettere in attesa i depositari

Dopo aver finalizzato i depositari e le origini dati che si desidera aggiungere al caso, è possibile facoltativamente mettere in attesa alcuni o tutti i depositari. Quando si attiva il blocco di un custode, il contenuto mappato a tale utente viene mantenuto finché non si rilascia il custode dalla causa o finché non si elimina l'esenzione. In alcuni casi, potrebbe essere necessario aggiungere i depositari a un caso senza bloccarli. 

Per posizionare i depositari e le origini dati selezionati in attesa:

1. Verificare le selezioni del custode e selezionare la casella di controllo per il blocco di ogni custode. Dopo che un custode è stato messo in attesa, verrà creato automaticamente un criterio di conservazione dei depositari contenente tutte le fonti detentive. Se l'opzione non è selezionata, il custode e le origini dati selezionate verranno aggiunti al caso, ma il contenuto non verrà conservato.

2. Passare alla scheda **esenzioni** e selezionare il **criterio**di conservazione dei depositari. 

3. Fare clic su **modifica** per visualizzare tutte le origini dati del custode selezionate.

    ![Esenzioni di posizione](../media/AddCustodianStep4.PNG)
