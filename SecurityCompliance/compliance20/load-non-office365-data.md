---
title: Caricare dati non Office 365 in un insieme da rivedere
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
ms.openlocfilehash: 60775002d5ebec83aacbec350a044b9d6ffeb461
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834961"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>Caricare dati non Office 365 in un insieme da rivedere

Non tutti i documenti che potrebbe essere necessario analizzare con Office 365 Advanced eDiscovery vivranno in Office 365. Con la caratteristica di importazione di contenuto non Office 365 in Advanced eDiscovery è possibile caricare documenti che non risiedono in Office 365 in un set di revisione in modo che vengano analizzati con Advanced eDiscovery. In questa procedura viene illustrato come portare i documenti non Office 365 in Advanced eDiscovery per l'analisi.

>[!Note]
>Advanced eDiscovery richiede un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione. Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile iscriversi per una versione di valutazione di Office 365 Enterprise E5.

## <a name="before-you-begin"></a>Informazioni preliminari

Se si utilizza la funzionalità carica non Office 365, come descritto in questo articolo, è necessario disporre di quanto segue:

- Un abbonamento a Office 365 o Microsoft 365 E5 o un abbonamento E3 con l'abbonamento al componente aggiuntivo per la conformità avanzato.

- Tutti i depositari il cui contenuto non Office 365 verrà caricato devono disporre di una licenza E3 con una licenza per il componente aggiuntivo per la conformità avanzata o con una licenza E5.

- Un caso avanzato di eDiscovery esistente.

- I depositari devono essere aggiunti al caso prima di caricare i dati non di Office 365 associati.

- Tutti i file che verranno caricati devono trovarsi in cartelle, in cui ogni cartella è associata a un determinato custode. I nomi di queste cartelle devono utilizzare il formato di denominazione seguente: *alias @ NomeDominio*. L' *alias @ NomeDominio* deve essere l'alias e il dominio dell'utente di Office 365. È possibile raccogliere tutte le cartelle *alias @ DomainName* in una cartella radice. La cartella radice può contenere solo le cartelle *alias @ DomainName* ; non sono consentiti file sciolti nella cartella radice.

   Ad esempio, la struttura di cartelle per i dati non di Office 365 che si desidera caricare sarebbe simile alla seguente:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Dove abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com sono gli indirizzi SMTP dei depositari nel caso.

   ![Struttura di cartelle di caricamento dei dati non Office 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Un account che sia un Manager di eDiscovery o un amministratore di eDiscovery

- Strumenti di archiviazione di Microsoft Azure installati in un computer che ha accesso alla struttura di cartelle di contenuto non di Office 365.

- Installare AzCopy, operazione che è possibile eseguire da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Caricare il contenuto non Office 365 in Advanced eDiscovery

1. Come eDiscovery Manager o amministratore di eDiscovery, aprire Advanced eDiscovery, quindi il caso in cui i dati non di Office 365 verranno caricati.  Fare clic sulla scheda **revisione dei set** , quindi selezionare il set di revisione in cui si desidera caricare i dati non di Office 365.  Se non è stato ancora creato un set di revisione, è possibile farlo adesso.  Infine, fare clic su **Gestisci Revisione set** e quindi su **Visualizza caricamenti** nel riquadro dei dati * * non Office 365.

2. Fare clic sul pulsante **Carica file** per avviare l'importazione guidata dati non di Office 365.

   ![Caricare file](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Il primo passaggio della procedura guidata consente di preparare semplicemente un BLOB di Azure sicuro per i file da caricare.  Una volta completata la preparazione, fare clic sul pulsante **Avanti: carica file** .

   ![Importazione non Office 365-preparazione](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Nel passaggio **file di caricamento** specificare il **percorso dei file**, in cui si trovano i dati non di Office 365 pianificati per l'importazione.  L'impostazione del percorso corretto garantisce che il comando AzCopy sia stato aggiornato correttamente.

   > [!NOTE]
   > Se AzCopy non è ancora stato installato, è possibile eseguire questa operazione da qui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copiare il comando predefinito facendo clic sul collegamento **copia in Appunti** . Avviare un prompt dei comandi di Windows, incollare il comando e premere INVIO.  I file verranno caricati nell'archiviazione BLOB di Azure sicura per il passaggio successivo.

   ![Importazione/caricamento di file non di Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![Non Office 365 Import-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Se il comando AzCopy fornito ha esito negativo, fare riferimento a [risoluzione dei problemi AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)

6. Infine, tornare alla conformità & sicurezza e fare clic sul pulsante **Avanti: elabora file** .  Verrà avviata l'elaborazione, l'estrazione del testo e l'indicizzazione dei file caricati.  È possibile tenere conto dello stato di avanzamento dell'elaborazione qui o nella scheda **processi** .  Una volta completato, i nuovi file saranno disponibili nel set di revisione.  Dopo aver completato l'elaborazione, è possibile chiudere la procedura guidata.

   ![File del processo di importazione non Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

