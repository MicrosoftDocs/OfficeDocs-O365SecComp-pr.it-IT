---
title: Gestire i depositari in un caso avanzato di eDiscovery (anteprima)
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
ms.openlocfilehash: 6a21240f71c64f244ee42c3d3a2ed9d75381edaa
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241853"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a>Gestire i depositari in un caso avanzato di eDiscovery (anteprima)

La scheda depositari contiene un elenco ordinabile di tutti i depositari nel caso. Dopo aver aggiunto i depositari a un caso, i dettagli relativi a ogni custode verranno raccolti automaticamente da Azure Active Directory.

![Gestire i depositari](../media/CustodianDetails.PNG)

## <a name="viewing-custodian-details"></a>Visualizzazione dei dettagli del custode

Dopo aver aggiunto un custode a un caso e averli selezionati nell'elenco della scheda **depositari** , viene visualizzata la pagina del riquadro a comparsa contenente i dettagli del custode. Da qui, è possibile visualizzare tutti i dettagli relativi a quel custode. La pagina del riquadro a comparsa contiene i campi seguenti:

- Informazioni di contatto

  - **Nome**visualizzato: il nome visualizzato nella rubrica per il custode. Questo è in genere la combinazione del nome, dell'iniziale e del cognome del custode.
  - **Posta/SMTP**: indirizzo SMTP per il custode, ad esempio Jeff@contoso.onmicrosoft.com.  
  - **Titolo**: titolo del processo del custode.
  - **Reparto**: il nome del reparto in cui lavora il custode.
  - **Manager**: il responsabile della banca depositaria. Il responsabile designato riceverà eventuali comunicazioni di esCalation per questo custode.
  
- Informazioni sulle posizioni

  - **Città**: la città in cui si trova il custode.
  - **Stato**: lo stato o la provincia nell'indirizzo del custode.
  - **Paese/area**geografica: il paese/area geografica in cui si trova il custode; ad esempio, "US" o "UK".
  - **Office**: la sede dell'ufficio nel luogo di lavoro del custode.

- Informazioni sul caso

  - **Stato blocco**: indica se il custode è stato messo in attesa. 
  - **Stato della comunicazione**: indica se il custode ha emesso un avviso di esenzione. Se il custode ha emesso un avviso, questo verrà contrassegnato come *pubblicato*. Se al custode non è stato emesso un avviso, lo stato non verrà *pubblicato*. 
  - **Status**: lo stato del custode all'interno del caso. Questo sarà *attivo* se il custode è ancora in attesa per il caso. Se un custode è stato rimosso da un caso, il relativo stato verrà modificato in *rilasciato*. 

- Stato di elaborazione

  - **Stato**di indicizzazione: indica lo stato del processo di indicizzazione Deep.  
  - **IndexIng Last updated Time**: indica la DateStamp di quando è stato attivato l'ultimo processo di indicizzazione Deep.
  - **Origini dati**: Visualizza il numero di cassette postali, siti e team selezionati per il custode.

## <a name="editing-a-custodian"></a>Modifica di un custode

Man mano che il caso progredisce, è possibile rilevare che potrebbero essere presenti ulteriori origini dati rilevanti per un determinato custode & il caso. In altri scenari potrebbe essere necessario rimuovere determinate origini dati che sono state esaminate e ritenute irrilevanti.

Per aggiornare un custode e le origini dati selezionate:

1. Selezionare un caso esistente dall' **eDiscovery _GT_ Advanced eDiscovery (Preview)**.
  
2. Nel caso, fare clic sulla scheda **depositari** .
  
3. Selezionare il custode o i depositari dall'elenco e fare clic su **modifica origini**.

    ![Modificare origini dati](../media/EditCustodianDataSource.PNG)
  
4. Consente di aggiornare le selezioni per i percorsi di Exchange e OneDrive facendo clic su **Scegli origini dati**.
  
5. Aggiunta o rimozione di Team, SharePoint o cassette postali di Exchange mappati dall'utente facendo clic per **selezionare origini dati aggiuntive**. Per ulteriori informazioni su come eseguire il mapping delle origini dati a un custode, vedere [aggiungere i depositari a un caso](add-custodians-to-case.md).
  
6. Per aggiornare lo stato di conservazione dei depositari, fare clic su **Archivia esenzioni detentive**e abilitare o disabilitare il blocco per i depositari.

> [!TIP]
> È possibile selezionare più depositari per eseguire azioni in blocco, come la reindicizzazione, il rilascio o la modifica di un insieme di depositari.

## <a name="resolving-custodian-processing-errors"></a>Risoluzione degli errori di elaborazione del custode

Nella maggior parte dei flussi di lavoro legali, dopo l'aggiunta di depositari per un'indagine specifica, verrà eseguita una ricerca in un sottoinsieme di dati degli utenti. A causa di grandi dimensioni o possibili danneggiamenti, alcuni elementi all'interno delle origini dati dei depositari possono essere parzialmente indicizzati. Utilizzando la funzionalità Advanced eDiscovery (Preview) Deep indicizzazione, questi elementi parzialmente indicizzati possono essere corretti automaticamente tramite la ricerca per indicizzazione e la reindicizzazione di questi elementi su richiesta. 

Quando un custode viene aggiunto a un caso, i relativi dati vengono automaticamente "indicizzati in profondità", consentendo agli utenti di lasciare tali elementi parzialmente indicizzati anziché dover scaricare, correggere e rieseguire le ricerche al di fuori di Office 365. Durante il ciclo di vita di un caso, un utente può correggere gli elementi o aggiungere nuove origini dati per un determinato custode. Potrebbe essere necessario aggiornare l'indice del custode. 

Per attivare un processo di reindicizzazione per indirizzare gli elementi parzialmente indicizzati:

1. Passare a **eDiscovery _GT_ Advanced eDiscovery (Preview)** e selezionare un caso esistente.

2. Nel caso, fare clic su per la **scheda depositari**. 

3. Selezionare il custode o i depositari che devono essere reindicizzati e quindi fare clic su ![Indice di aggiornamento](../media/UpdateIndex.PNG) nella pagina a comparsa.

4. Controllare lo stato dell'indice del custode facendo clic sul collegamento nella colonna **stato processo** di indicizzazione nella scheda **depositari** .  

5. Lo stato del processo di reindicizzazione può essere rilevato anche nella scheda **processi** .

Per ulteriori informazioni su come reindicizzare e correggere gli elementi parzialmente indicizzati, vedere [Fix Processing Errors](processing-data-for-case.md).

## <a name="releasing-a-custodian-from-a-case"></a>Rilascio di un custode da un caso

Un custode viene rilasciato in situazioni in cui un caso è chiuso, un custode non è più in dovere di preservare il contenuto di un caso o quando un custode è ritenuto non più pertinente a un caso specifico. 

Se si rilascia un custode dopo la pubblicazione di un avviso di esenzione, verrà inviato un avviso di rilascio al custode. Inoltre, verranno rimossi anche tutti gli appigli detentivi attribuiti ai depositari rilasciati.

Se il custode è stato collocato in una posizione invisibile all'utente, in cui non sono state rilasciate notifiche di archiviazione legale, verranno rimossi tutti i resti di custodia attribuiti ai depositari rilasciati.  

Per rilasciare un custode: 

1.  Passare alla scheda **depositari** .

2.  Seleziona il custode dall'elenco e fai clic su ![Rilascia il custode](../media/ReleaseCustodian.PNG) nella pagina a comparsa.

    Lo stato del custode nella scheda **depositari** è impostato su **rilasciato** e lo **stato di blocco** sulla pagina del riquadro a comparsa viene modificato in **inattivo**. 

> [!TIP]
> Un custode potrebbe essere coinvolto contemporaneamente in diverse questioni legali. Quando un custode viene rilasciato da un caso, le esenzioni e le notifiche su altre questioni non verranno influenzate.

## <a name="related-information"></a>Informazioni correlate

 - [Correzione degli errori durante l'elaborazione dei dati](error-remediation.md) 
- [Uso delle comunicazioni](managing-custodian-communications.md)
