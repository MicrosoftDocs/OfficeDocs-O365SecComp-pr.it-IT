---
title: Gestire depositari in un caso eDiscovery avanzate (Preview)
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
ms.openlocfilehash: cce823924502fa2617d7819dc0967733fbc072e0
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706097"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a>Gestire depositari in un caso eDiscovery avanzate (Preview)

La scheda depositari contiene un elenco di tutti i depositari nel caso può essere ordinato. Dopo aver aggiunto depositari a un caso, verranno raccolti automaticamente informazioni dettagliate su ogni depositaria da Azure Active Directory.

## <a name="viewing-custodian-details"></a>Visualizzazione dei dettagli depositaria

Dopo avere aggiunto un depositaria a un caso e selezionarli dall'elenco nella scheda **depositari** , viene visualizzata la pagina comparsa che contiene i dettagli depositaria. Da qui è possibile visualizzare tutti i dettagli relativi a tale depositaria. Nella pagina comparsa sono i seguenti campi:

- Informazioni di contatto

  - **Nome visualizzato**: il nome visualizzato nella Rubrica per il depositaria. Questa è in genere la combinazione del nome del depositaria, intermedio iniziale e cognome dell'utente.
  - **/ SMTP Mail**: indirizzo SMTP per depositaria, ad esempio jeff@contoso.onmicrosoft.com.  
  - **Titolo**: titolo professionale del depositaria.
  - **Reparto**: il nome per il reparto in cui lavora il depositaria.
  - **Manager**: responsabile della depositaria. Il manager designato ricevono tutte le comunicazioni Escalation per questo depositaria.
  
- Informazioni sulle posizioni

  - **Città**: città in cui si trova il depositaria.
  - **Informazioni sullo stato**: lo stato o la provincia nell'indirizzo del depositaria.
  - **Paese**: paese/area geografica in cui si trova; il depositaria ad esempio, "Usa" o "UK".
  - **Office**: l'ubicazione dell'ufficio sul posto di depositaria d'ufficio.

- Informazioni sul casi

  - **Stato esenzione**: indica se il depositaria è messe in attesa. 
  - **Lo stato di comunicazione**: indica se il depositaria è stata eseguita una notifica di attesa. Se il depositaria è stato rilasciato un avviso, questo verrà contrassegnato come *pubblicati*. Se il depositaria non è stato rilasciato un avviso, quindi questo stato saranno *rimosse*. 
  - **Stato**: lo stato di depositaria all'interno del case. Questo valore sarà *Attiva* se il depositaria è ancora in attesa per il case. Se un depositaria viene rimosso da un caso, il relativo stato verrà modificato in *rilasciato*. 

- Stato di elaborazione

  - **Lo stato di indicizzazione**: indica lo stato del processo di indicizzazione completa.  
  - **Indicizzazione l'ultima volta aggiornati**: indica datestamp dell'ultima attivazione quando il processo di indicizzazione completa.
  - **Origini dati**: Visualizza il numero di cassette postali, i siti e i team che sono stati selezionati per la depositaria.

## <a name="updating-a-custodian"></a>Aggiornamento di un depositaria

Durante l'avanzamento maiuscole, si potrebbe scoprire che potrebbero esserci altre origini dati rilevanti per un & depositaria specifici al caso. In altri scenari, si desidera rimuovere alcune origini dati che sono stati esaminati e considerati come non rilevanti.

Per aggiornare un depositaria e le origini dati selezionati:

1. Selezionare un caso esistente **eDiscovery gt _ avanzate eDiscovery (Preview)**.
  
2. Nel caso, fare clic sulla scheda **depositari** .
  
3. Selezionare il custodian(s) dall'elenco e fare clic su **Modifica origini**.
  
4. Aggiornare le selezioni per i percorsi di Exchange e OneDrive facendo clic su **origini dati scegliere**.
  
5. Aggiungere o rimuovere i team, SharePoint o Exchange le cassette postali mappato all'utente fare clic per **selezionare origini dati aggiuntive**. Per ulteriori informazioni su come è possibile mappare i dati origini a un depositaria, vedere [Add depositari a un caso](add-custodians-to-case.md).
  
6. Per aggiornare lo stato di conservazione depositaria, fare clic su **archiviazioni sul posto detentive**e abilitare o disabilitare l'archiviazione per depositari.

> [!TIP]
> È possibile selezionare più depositari per eseguire le operazioni in blocco, ad esempio la reindicizzazione, rilascio o modifica di un set di depositari.

## <a name="resolving-custodian-processing-errors"></a>Risoluzione degli errori di elaborazione depositaria

Nella maggior parte dei flussi di lavoro legali, dopo l'aggiunta di depositari per il controllo specifico, un sottoinsieme di dati degli utenti verrà eseguita la ricerca. A causa di dimensioni dei file di grandi dimensioni o danneggiamento dei possibile, alcuni elementi all'interno di origini dati degli depositari potrebbero essere parzialmente indicizzati. Utilizzando la funzionalità di indicizzazione completa di eDiscovery avanzate (anteprima), questi elementi indicizzati parzialmente possono essere automaticamente risolte nuovamente la ricerca per indicizzazione e la reindicizzazione questi elementi su richiesta. 

Quando un depositaria viene aggiunto a un caso, i dati vengono automaticamente "estensione indicizzati", che consente agli utenti di lasciare queste parzialmente indicizzato elementi sul posto evita di dover scaricare, correggere ed eseguire di nuovo le ricerche all'esterno di Office 365. Durante il ciclo di vita di un caso, l'utente può correggere gli elementi o aggiungere nuove origini dati per un determinato depositaria. Ciò può richiedere l'indice depositaria da aggiornare. 

Per attivare un processo di indicizzazione nuovamente all'indirizzo parzialmente voci indicizzate:

1. Passare a **eDiscovery gt _ avanzate eDiscovery (Preview)** e selezionare un caso esistente.

2. Nel caso, fare clic su scheda **depositari**. 

3. Selezionare custodian(s) che deve essere reindicizzazione e quindi fare clic su **Aggiorna indice** nella pagina del riquadro a comparsa.

4. Controllare lo stato dell'indice depositaria facendo clic sul collegamento nella colonna **stato processo di indicizzazione** nella scheda **depositari** .  

5. Tenere traccia dello stato per il processo di indicizzazione nuovamente anche nella scheda **processi** .

Per ulteriori informazioni sugli elementi indicizzati parzialmente monitorando e la nuova indicizzazione, vedere [correggere gli errori di elaborazione](processing-data-for-case.md).

## <a name="releasing-a-custodian-from-a-case"></a>Rilasciare un depositaria dal caso

Viene rilasciato un depositaria nei casi in cui un caso viene chiuso, un depositaria non è più obbligo di conservare il contenuto per un caso o quando un depositaria viene ritenuta su no più essere pertinenti per una determinata caso. 

Se si rilascia un depositaria dopo la pubblicazione di un avviso di attesa, verrà inviato un avviso di versione per il depositaria. Inoltre, qualsiasi esenzioni detentive attribuite alle depositari rilasciate anche da rimuovere.

Se il depositaria è stato messo in un'esenzione invisibile all'utente, cui non sono state inviate le notifiche di conservazione a fini giudiziari, vengono rimosse le esenzioni detentive attribuite alle depositari rilasciati.  

Per rilasciare un depositaria: 

1.  Passare alla scheda **depositari** .

2.  Selezionare il depositaria dall'elenco e fare clic su **depositari versione** nella pagina del riquadro a comparsa.

    Lo stato di depositaria nella scheda **depositari** è impostato su **rilascio** e la **Stato esenzione** page comparsa viene modificato in **inattivo**. 

> [!TIP]
> Un depositaria potrebbe essere contemporaneamente essere coinvolto in materia di conservazione a fini giudiziari diversi. Quando viene rilasciato un depositaria dal caso, le esenzioni e le notifiche tra gli altri aspetti non essere interessate.

## <a name="related-information"></a>Informazioni correlate

 - [Correzione degli errori durante l'elaborazione dei dati](error-remediation.md) 
- [Uso delle comunicazioni](managing-custodian-communications.md)
