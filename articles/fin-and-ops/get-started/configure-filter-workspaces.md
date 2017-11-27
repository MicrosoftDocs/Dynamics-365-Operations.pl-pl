---
title: "Konfigurowanie i filtrowanie obszarów roboczych"
description: "Ten artykuł zawiera omówienie metod konfigurowania i filtrowania obszarów roboczych."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c90384c798023ac4fcab06502d77f832a8e4c4c2
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="configure-and-filter-workspaces"></a><span data-ttu-id="017cd-103">Konfigurowanie i filtrowanie obszarów roboczych</span><span class="sxs-lookup"><span data-stu-id="017cd-103">Configure and filter workspaces</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="017cd-104">Ten artykuł zawiera omówienie metod konfigurowania i filtrowania obszarów roboczych.</span><span class="sxs-lookup"><span data-stu-id="017cd-104">This article provides an overview about how to configure and filter workspaces.</span></span>

<a name="configuring-a-workspace"></a><span data-ttu-id="017cd-105">Konfiguracja obszaru roboczego</span><span class="sxs-lookup"><span data-stu-id="017cd-105">Configuring a workspace</span></span>
-----------------------

<span data-ttu-id="017cd-106">Można zmienić wygląd i zachowanie niektórych obszarów roboczych poprzez aktualizację ustawień mających zastosowanie do całego obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="017cd-106">You can change the appearance and behavior of some workspaces by updating settings that apply to the whole workspace.</span></span> <span data-ttu-id="017cd-107">Jeśli obszar roboczy można skonfigurować, w okienku akcji znajduje się przycisk z instrukcją, że jego kliknięcie pozwoli dokonać zmian w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="017cd-107">When a workspace can be configured, the Action Pane includes a button that instructs you to click it to make configuration changes.</span></span> <span data-ttu-id="017cd-108">Na przykład na poniższej ilustracji przycisk ma nazwę **Konfiguruj mój obszar roboczy**.</span><span class="sxs-lookup"><span data-stu-id="017cd-108">For example, in the following illustration, the button is named **Configure my workspace**.</span></span> 

<span data-ttu-id="017cd-109">[![configure-and-filter-workspaces](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="017cd-109">[![configure-and-filter-workspaces](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)</span></span>   

<span data-ttu-id="017cd-110">Po kliknięciu przycisku pojawia się okno dialogowe, gdzie można zmodyfikować wstępnie zdefiniowane ustawienia obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="017cd-110">When you click the button, a dialog appears, where you can modify the predefined settings for the workspace.</span></span> <span data-ttu-id="017cd-111">Konkretne ustawienia widoczne w tym oknie zależą od obszaru roboczego oraz od formantów i danych biznesowych dostępnych w obszarze.</span><span class="sxs-lookup"><span data-stu-id="017cd-111">The specific settings that you see in this dialog vary by workspace, and depend on the specific controls and business data that are available in the workspace.</span></span> 

<span data-ttu-id="017cd-112">[![configure-my-workspace](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span><span class="sxs-lookup"><span data-stu-id="017cd-112">[![configure-my-workspace](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)</span></span>

## <a name="filtering-a-workspace"></a><span data-ttu-id="017cd-113">Filtrowanie obszaru roboczego</span><span class="sxs-lookup"><span data-stu-id="017cd-113">Filtering a workspace</span></span>
<span data-ttu-id="017cd-114">W wielu obszarach można filtrować wyświetlaną w nich zawartość.</span><span class="sxs-lookup"><span data-stu-id="017cd-114">Many workspaces let you filter the content that appears in them.</span></span> <span data-ttu-id="017cd-115">Dostępne formanty mogą pozwalać na filtrowanie całej zawartości obszaru lub tylko zawartości z określonej części obszaru.</span><span class="sxs-lookup"><span data-stu-id="017cd-115">The controls that are available might let you filter all the content in the workspace or only the content in a specific section of the workspace.</span></span> <span data-ttu-id="017cd-116">Filtry w obszarze roboczym mogą mieć postać pól wyszukiwania, kombi, tekstu w formacie dowolnym i innych.</span><span class="sxs-lookup"><span data-stu-id="017cd-116">The filters on workspaces can be lookups, combo boxes, free-form text fields, or other types of controls.</span></span> <span data-ttu-id="017cd-117">Jednak każdy typ filtru ma takie same skutki, jak opisano w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="017cd-117">However, every type of filter has the same effects, as described in the following sections.</span></span>

### <a name="workspace-wide-filters"></a><span data-ttu-id="017cd-118">Filtr całego obszaru roboczego</span><span class="sxs-lookup"><span data-stu-id="017cd-118">Workspace-wide filters</span></span>

<span data-ttu-id="017cd-119">Za pomocą filtra całego obszaru roboczego można filtrować cały obszar.</span><span class="sxs-lookup"><span data-stu-id="017cd-119">You can filter the whole workspace by using a workspace-wide filter.</span></span> <span data-ttu-id="017cd-120">Filtr całego obszaru roboczego znajduje się w lewym górnym rogu obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="017cd-120">A workspace-wide filter appears in the upper-left corner of the workspace.</span></span> <span data-ttu-id="017cd-121">Gdy zaznaczysz określoną wartość na liście rozwijanej, zawartość obszaru roboczego będzie filtrowana na podstawie tego wyboru.</span><span class="sxs-lookup"><span data-stu-id="017cd-121">When you select a specific value in the drop-down list, the contents of the workspace are filtered based on that selection.</span></span> 

<span data-ttu-id="017cd-122">[![workspace-filter](./media/workspace-filter.png)](./media/workspace-filter.png)</span><span class="sxs-lookup"><span data-stu-id="017cd-122">[![workspace-filter](./media/workspace-filter.png)](./media/workspace-filter.png)</span></span> 

<span data-ttu-id="017cd-123">Jeśli klikniesz, aby otworzyć filtr, zobaczysz szereg opcji.</span><span class="sxs-lookup"><span data-stu-id="017cd-123">When you click to open the filter, you're presented with several options.</span></span> 

<span data-ttu-id="017cd-124">[![workspace-filter-expanded](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span><span class="sxs-lookup"><span data-stu-id="017cd-124">[![workspace-filter-expanded](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)</span></span> 

<span data-ttu-id="017cd-125">Wybierz opcję, aby na jej podstawie przefiltrować obszar roboczy.</span><span class="sxs-lookup"><span data-stu-id="017cd-125">Select an option to filter the workspace based on that option.</span></span>

### <a name="workspace-section-filters"></a><span data-ttu-id="017cd-126">Filtry sekcji obszaru roboczego</span><span class="sxs-lookup"><span data-stu-id="017cd-126">Workspace section filters</span></span>

<span data-ttu-id="017cd-127">Jeśli poszczególne sekcje obszaru roboczego mają własne filtry, każdą sekcję można filtrować oddzielnie.</span><span class="sxs-lookup"><span data-stu-id="017cd-127">If individual sections of the workspace have filters, you can filter each section separately.</span></span> <span data-ttu-id="017cd-128">Na ilustracji poniżej filtr (pole z napisem „Filtr”) jest przykładem filtra pola tekstu w formacie dowolnym.</span><span class="sxs-lookup"><span data-stu-id="017cd-128">In the following illustration, the filter (the field that contains the text "Filter") is an example of a free-form text field filter.</span></span> 

<span data-ttu-id="017cd-129">[![workspace-section-filters](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span><span class="sxs-lookup"><span data-stu-id="017cd-129">[![workspace-section-filters](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)</span></span> 

<span data-ttu-id="017cd-130">Podobnie jak w przypadku filtra całego obszaru roboczego, wybierz lub wprowadź wartość, aby według niej wyfiltrować zawartość sekcji.</span><span class="sxs-lookup"><span data-stu-id="017cd-130">As with a workspace-wide filter, select or enter a value in the field to filter the contents of the section.</span></span>




