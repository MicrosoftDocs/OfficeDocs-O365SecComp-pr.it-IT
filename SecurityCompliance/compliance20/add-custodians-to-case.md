---
title: Aggiungere depositari a un caso eDiscovery avanzate (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9a7dc6b1c2eeffdcd49be64d1d09d4a2bda782b
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607919"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>Aggiungere una ricerca eDiscovery avanzate (Preview) depositari Case

Utilizzo di eDiscovery avanzate (anteprima), è possibile utilizzare lo strumento di gestione incorporati depositaria per coordinare i flussi di lavoro intorno a gestione depositari e identificare le origini dati rilevanti, detentive all'interno di un caso. Quando si aggiunge un depositaria, il sistema può automaticamente identificare e archiviazioni sul posto alle loro cassette postali di Exchange primaria e OneDrive per sito aziendale. Come di procedere con l'individuazione, si potrebbe Scopri e mappare le cassette postali di altri o siti che un depositaria a cui si accede al passato o team che un depositaria appartenga alla data odierna.

Utilizzare il flusso di lavoro seguente per aggiungere e gestire depositari in casi di eDiscovery avanzate (Preview) all'interno di sicurezza & centro conformità. 

## <a name="step-1-identify-potential-custodians"></a>Passaggio 1: Identificare potenziali depositari

Il primo passaggio consiste nel identificare depositari appropriati per la materia. Per aggiungere depositari a un caso, è necessario essere un membro di eDiscovery Manager o un gruppo di ruoli di eDiscovery Admins.   

Per aggiungere depositari a un caso eDiscovery avanzate (Preview) esistenti:

1. Nella pagina **eDiscovery avanzate (anteprima)** , andare al caso.
 
2. Dopo aver selezionato un caso, passare alla scheda **depositari** e fare clic su **Aggiungi depositaria +**. 
 
3. Scegliere depositari che si desidera aggiungere al caso. È possibile avviare digitando per cercare e selezionare gli utenti Azure Active Directory dell'organizzazione.
 
4. Dopo avere scelto l'elenco dei depositari, fare clic su **Avanti** per iniziare a identificare possibili origini dati. 
   
## <a name="optional-step-2-select-custodian-data-sources"></a>(Facoltativo) Passaggio 2: Selezionare le origini dati depositaria

Dopo aver aggiunto depositari a un caso, è possibile utilizzare Office 365 che consentono di identificare e mantenere le origini dati depositaria principale. Il prossimo passaggio del flusso di lavoro consiste nel selezionare le origini dati e di proprietà di depositari specificati nel passaggio 1. 

Per identificare le origini dati depositaria: 

1. Per ogni depositaria selezionare **Exchange** se si desidera che il sistema per identificare e aggiungere cassette postali di Exchange primaria del depositaria automaticamente. 
 
2. Per ogni depositaria selezionare **OneDrive** se si desidera che il sistema per identificare e aggiungere URL OneDrive primario del depositaria automaticamente. 

    Dopo aver apportato le selezioni effettuate, essi sistema tenterà di identificare le origini dati e aggiungerli al caso automaticamente.
 
4. Fare clic su **Avanti** per iniziare il mapping di origini dati aggiuntive per la depositaria.

## <a name="optional-step-3-map-additional-data-sources"></a>(Facoltativo) Passaggio 3: Eseguire il mapping di origini dati aggiuntive

In base al caso, è anche possibile aggiungere cassette postali che un determinato depositaria potrebbe essere utilizzati in passato, gruppi di cui una depositaria attualmente è un membro o i siti che un depositaria hanno accesso a in passato. Oltre alle origini dati depositaria principale, è possibile aggiungere ulteriori origini di dati di Office 365 per un depositaria o utilizzare Office 365 per aiutare a identificare le origini dati potenzialmente pertinenti anche. 

Per mappare le cassette postali, siti o team a un depositaria specifico:
1. Selezionare **aggiornamento** per assegnare i percorsi di contenuti, ad esempio le cassette postali, i siti e i team, a un depositaria specifico. 

2. Nell'elemento libero, specificare quanto segue:
   
  -  **Cassette postali di Exchange** - fare clic su **Scegli utenti, gruppi o team** e quindi fare clic nuovamente su **Scegli utenti, gruppi o team** . Per specificare le cassette postali per assegnare a depositaria selezionato, utilizzare la casella Cerca per trovare cassette postali degli utenti e gruppi di distribuzione. È inoltre possibile assegnare la cassetta postale associata per un Team di Microsoft o un gruppo di Office 365. Selezionare la casella di controllo team utente, gruppo, fare clic su **Scegli**e quindi fare clic su **Fine**.

      > [!NOTE]
      > Quando si fa clic su Scegli utenti, gruppi o team per specificare le cassette postali, la selezione delle cassette postali che viene visualizzata sia vuota. Questo è per impostazione predefinita per migliorare le prestazioni. Per aggiungere persone all'elenco, digitare un nome (almeno 3 caratteri) nella casella di ricerca.
     
   - **Siti di SharePoint** - fare clic su **Scegli siti** e quindi **Scegliere siti** per specificare ulteriori SharePoint e OneDrive per i siti che si desidera assegnare al depositaria selezionato. È inoltre possibile aggiungere l'URL del sito di SharePoint per un Team di Microsoft o un gruppo di Office 365. Digitare l'URL per ogni sito che si desidera assegnare. Fare clic su **Scegli**e quindi fare clic su **Fine**.
   - **Team di Microsoft** – fare clic su **Scegliere i team** e quindi fare clic su **Team scegliere** nuovamente per visualizzare un elenco di gruppi di Team Microsoft che il depositaria appartenga alla data odierna. Selezionare il team che si desidera aggiungere il depositaria. Una volta selezionato, il sistema identificherà automaticamente & selezionare che il sito di SharePoint e cassetta postale di gruppo associato associate a tale Team di Microsoft. Fare clic su **Scegli**e quindi fare clic su **Fine**.
        
      > [!NOTE]
      > Per aggiungere ulteriori Teams Microsoft, è necessario aggiungere separatamente le cassette postali e il sito di SharePoint come illustrato in precedenza.

Dopo avere origini di mapping, è possibile visualizzare il totale delle cassette postali, i siti e i team per depositari appena aggiunto. Quando aver completato le origini dati pertinenti per una specifica depositaria, questo mapping verrà gestito ed estesa alla raccolta di eDiscovery, l'elaborazione e i flussi di lavoro di revisione. 

## <a name="optional-step-4-place-custodians-on-hold"></a>(Facoltativo) Passaggio 4: Posto depositari in attesa

 Dopo avere scelto il depositari e origini dati che si desidera aggiungere al case, facoltativamente è possibile effettuare alcune o tutte le depositari in attesa. Quando si effettua una depositaria in attesa, il contenuto mappato a tale utente viene mantenuto finché non si rilascia depositaria dal case o finché non viene eliminato l'attesa. In alcuni casi, si desidera aggiungere depositari a un caso senza in cui vengono posizionati in attesa. 

Per mettere il selezionato depositari e le origini dati in attesa:

1. Verificare le selezioni effettuate depositaria e selezionare checkox posizionare ciascun depositaria in attesa. Una volta che un depositaria viene messa in attesa, verrà creato automaticamente un criterio di conservazione depositaria contenente detentive tutte le origini. Se l'opzione non è selezionata, le origini dati di depositaria & selezionata verranno aggiunto al caso ma non verrà mantenuto il contenuto.

2. Passare alla scheda **contiene** e selezionare il **Criterio di conservazione depositaria**. 

3. Fare clic su **Modifica** per visualizzare tutte le origini dati depositaria selezionato.
