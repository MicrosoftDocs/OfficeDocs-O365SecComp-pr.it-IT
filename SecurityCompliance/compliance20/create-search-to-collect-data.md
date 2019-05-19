---
title: Creare una ricerca per raccogliere dati
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 360ba6a67d43a0b78b1104ae64885697009bb222
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155108"
---
# <a name="create-a-search-to-collect-data"></a><span data-ttu-id="16a3f-102">Creare una ricerca per raccogliere dati</span><span class="sxs-lookup"><span data-stu-id="16a3f-102">Create a search to collect data</span></span>

<span data-ttu-id="16a3f-103">Nella scheda **ricerche** del caso, è possibile creare una nuova ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="16a3f-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

## <a name="name-your-search-and-give-description"></a><span data-ttu-id="16a3f-104">Denominare la ricerca e fornire una descrizione</span><span class="sxs-lookup"><span data-stu-id="16a3f-104">Name your search and give description</span></span>

<span data-ttu-id="16a3f-105">Ogni ricerca con un caso deve avere un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="16a3f-105">Each search with a case should have a unique name.</span></span> <span data-ttu-id="16a3f-106">Facoltativamente, è possibile fornire una descrizione per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="16a3f-106">You can optionally provide a description for your search.</span></span> 

## <a name="define-your-conditions"></a><span data-ttu-id="16a3f-107">Definire le proprie condizioni</span><span class="sxs-lookup"><span data-stu-id="16a3f-107">Define your conditions</span></span>

<span data-ttu-id="16a3f-108">È possibile definire le condizioni per la ricerca utilizzando le schede delle condizioni predefinite o utilizzando KQL (Keyword Query Language).</span><span class="sxs-lookup"><span data-stu-id="16a3f-108">You can define the conditions for your search using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="16a3f-109">Per ulteriori informazioni, vedere [creazione di query di ricerca](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="16a3f-109">For more information, see [Build search queries](building-search-queries.md).</span></span>

## <a name="choose-the-custodians-to-search-from"></a><span data-ttu-id="16a3f-110">Scegliere i depositari da cui eseguire la ricerca</span><span class="sxs-lookup"><span data-stu-id="16a3f-110">Choose the custodians to search from</span></span>

<span data-ttu-id="16a3f-111">Dopo aver definito le condizioni, è necessario scegliere quali posizioni si desidera ricercare.</span><span class="sxs-lookup"><span data-stu-id="16a3f-111">Once you have defined your conditions, you need to choose which locations you want to search.</span></span> <span data-ttu-id="16a3f-112">Un modo per farlo è specificare quali depositari sono già stati aggiunti al caso in cui si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="16a3f-112">One way to do it is by specifying which custodians you have already added to the case you want to search.</span></span> <span data-ttu-id="16a3f-113">Selezionando un custode, verrà eseguita la ricerca in tutte le origini dati mappate al custode.</span><span class="sxs-lookup"><span data-stu-id="16a3f-113">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="16a3f-114">Per ulteriori informazioni su come aggiungere depositari al caso e gestire le origini dati, vedere [collaborare con i depositari](managing-custodians.md) .</span><span class="sxs-lookup"><span data-stu-id="16a3f-114">See [Work with custodians](managing-custodians.md) for more information on how to add custodians to your case and manage their data sources.</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="16a3f-115">Scegliere le posizioni non detentive</span><span class="sxs-lookup"><span data-stu-id="16a3f-115">Choose non-custodial locations</span></span>

<span data-ttu-id="16a3f-116">In alcuni casi, è possibile cercare le origini dati che non vengono mappate a un custode.</span><span class="sxs-lookup"><span data-stu-id="16a3f-116">In some cases, you may wish to search data sources that are not mapped to a custodian.</span></span> <span data-ttu-id="16a3f-117">In questo caso, è possibile specificare i percorsi che si desidera ricercare oppure scegliere di cercare tutti i percorsi di contenuto per uno specifico servizio di Office 365, ad esempio la ricerca in tutte le cassette postali di Exchange o in tutti i siti di SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="16a3f-117">In this case, you can specify the locations you would like to search, or choose to search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or all SharePoint and OneDrive for Business sites).</span></span>