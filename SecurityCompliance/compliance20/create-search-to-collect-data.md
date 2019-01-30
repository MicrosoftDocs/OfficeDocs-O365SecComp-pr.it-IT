---
title: Creazione di una ricerca per raccogliere dati
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
ms.openlocfilehash: 3ebb9a40d3fb055fbb88b32175a4a22df3da44af
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607947"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="db827-102">Creazione di una ricerca per raccogliere dati</span><span class="sxs-lookup"><span data-stu-id="db827-102">Create a search to collect data</span></span>

<span data-ttu-id="db827-103">Nella scheda **ricerche** nel caso, è possibile creare una nuova ricerca facendo clic su **New search** e seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="db827-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="db827-104">Nome della ricerca e fornire descrizione</span><span class="sxs-lookup"><span data-stu-id="db827-104">Name your search and give description</span></span>

<span data-ttu-id="db827-p101">Ogni ricerca con un caso deve avere un nome univoco. È facoltativamente possibile fornire una descrizione per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="db827-p101">Each search with a case should have a unique name. You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="db827-107">Definire le condizioni</span><span class="sxs-lookup"><span data-stu-id="db827-107">Define your conditions</span></span>

<span data-ttu-id="db827-p102">È possibile definire le condizioni per la ricerca utilizzando le schede condizione preesistente o utilizzando Keyword Query Language (KQL). Per ulteriori informazioni, vedere [creare query di ricerca](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="db827-p102">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL). For more information, see [Building search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="db827-110">Scegliere depositari eseguire la ricerca</span><span class="sxs-lookup"><span data-stu-id="db827-110">Choose the custodians to search from</span></span>

<span data-ttu-id="db827-p103">Dopo aver definito le condizioni, è necessario scegliere quali percorsi da cercare. Per eseguire questa operazione è specificando quali depositari è già stato aggiunto al caso si desidera eseguire la ricerca. Selezionando un depositaria, si eseguirà la ricerca con tutte le origini dati mappate al depositaria. Per ulteriori informazioni su come aggiungere depositari al case e gestire le origini dati, vedere [Working with depositari](managing-custodians.md) .</span><span class="sxs-lookup"><span data-stu-id="db827-p103">Once you have defined your conditions, you need to choose which locations you want to search. One way to do it is by specifying which custodians you have already added to the case you want to search. By selecting a custodian, you will run the search against all data sources mapped to the custodian. See [Working with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="db827-115">Scegliere le posizioni non detentive</span><span class="sxs-lookup"><span data-stu-id="db827-115">Choose non-custodial locations</span></span>

<span data-ttu-id="db827-p104">In alcuni casi, si desidera cercare nelle origini dati che non vengono mappate a un depositaria. In questo caso, è possibile specificare i percorsi che si desidera eseguire la ricerca o scegliere di cercare tutti i percorsi di contenuti per un servizio specifico di Office 365 (ad esempio ricerca SharePoint e OneDrive di tutte le cassette postali di Exchange o tutti i siti di Business).</span><span class="sxs-lookup"><span data-stu-id="db827-p104">In some cases, you may wish to search data sources that are not mapped to a custodian. In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>