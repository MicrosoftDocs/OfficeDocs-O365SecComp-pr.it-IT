---
title: Caricare dati non Office 365 in un set di lavoro
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
ms.openlocfilehash: 1dad52075303450673e7f48b87e2952e35629a5e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706087"
---
# <a name="load-non-office-365-data-into-a-working-set"></a>Caricare dati non Office 365 in un set di lavoro

Non tutti i documenti che potrebbe essere necessario per l'analisi con Office 365 avanzate eDiscovery risiederanno in Office 365. Con il contenuto Non Office 365 importare funzionalità di eDiscovery avanzate che è possibile caricare documenti che non si trovano in Office 365 in un set di lavoro in modo che viene analizzato con eDiscovery avanzate. Questa procedura viene illustrato come portare i documenti non Office 365 in eDiscovery avanzate per l'analisi.

>[!Note]
>Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile richiedere una valutazione di Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Prima di iniziare
Utilizzando la caratteristica di caricamento Non Office 365, come descritto in questa procedura è necessario disporre:

- Un Office 365 E3 con sottoscrizione E5 o componente aggiuntivo di conformità avanzate.

- Tutti i depositari viene caricato il cui contenuto non Office 365 devono disporre E3 con licenze E5 o componente aggiuntivo di conformità avanzate.

- Un caso eDiscovery esistente.

- Tutti i file per caricamento raccolte in cartelle in cui vi è una cartella per depositaria e le cartelle è denominato in questo formato *alias@domainname* . *Alias@domainname* deve essere dominio e l'alias di utenti di Office 365. È possibile raccogliere tutte le cartelle *alias@domainname* in una cartella radice. La cartella radice può contenere solo le cartelle *alias@domainname* , non deve esistere alcun file separati nella cartella radice.

- Un account che rappresenta una ricerca eDiscovery Manager o eDiscovery amministratore Microsoft Azure Storage installati gli strumenti in un computer che dispone dell'accesso per la struttura di cartelle del contenuto non Office 365.

- Installare AzCopy, è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Caricare il contenuto non Office 365 in eDiscovery avanzate

1. Come eDiscovery Manager o eDiscovery amministratore, aprire eDiscovery avanzate e quindi caso in cui verranno caricati i dati non Office 365.  Fare clic sulla scheda **utilizzo di insiemi** e quindi selezionare il set di lavoro che si desidera caricare i dati Non Office 365.  Se non è già stato creato un gruppo di lavoro, è possibile farlo a questo punto.  Infine, fare clic su **Gestisci meccanismi impostata** il **caricamento Visualizza** nella sezione dati Non Office 365

2. Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati Non Office 365.

![Caricamento dei file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Il primo passaggio della procedura guidata prepara semplicemente blob Azure protetto per i file da caricare.  Dopo aver preparato compelted, fare clic sul **successivo: caricare i file** pulsante.

![Non Office 365 importazione - preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Nel passaggio **caricare i file** , specificare il **percorso dei file**, si tratta in cui si trovano i dati Non Office 365 che si prevede di importazione.  L'impostazione nella posizione corretta assicura AzCopy comando viene aggiornato in modo corretto.

> [!NOTE]
> Se non è già installato AzCopy, è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copiare il comando predefinito fare clic sul collegamento **Copia negli Appunti** . Avviare un prompt dei comandi di windows, incollare il comando e premere INVIO.  I file verranno caricati per l'archiviazione di blob Azure sicura per il passaggio successivo.

![Importazione non-Office 365 - caricamento file](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Importazione non Office 365 - AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Infine, tornare al & sicurezza conformità e fare clic sul **successivo: elaborazione dei file** pulsante.  Verrà avviata elaborazione, l'estrazione di testo e l'indicizzazione dei file caricati.  È possibile verificare lo stato di avanzamento dell'elaborazione di seguito o sulla scheda **processi** .  Al termine, i nuovi file sarà disponibili nel set di lavoro.  Una volta completata l'elaborazione, è possibile chiudere la procedura guidata.

![Importazione non-Office 365 - elaborare i file](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

