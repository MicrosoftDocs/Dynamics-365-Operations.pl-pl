---
title: Tworzenie zasady akumulacji kosztów
description: W tej procedurze pokazano, jak utworzyć zasadę akumulacji kosztów, a następnie reguły dla tej zasady.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b6d32cc2c1844c6c334dd00b249c736e153f13d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446936"
---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="c1547-103">Tworzenie zasady akumulacji kosztów</span><span class="sxs-lookup"><span data-stu-id="c1547-103">Create a cost rollup policy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c1547-104">W tej procedurze pokazano, jak utworzyć zasadę akumulacji kosztów, a następnie reguły dla tej zasady.</span><span class="sxs-lookup"><span data-stu-id="c1547-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="c1547-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="c1547-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="c1547-106">Tworzenie zasady</span><span class="sxs-lookup"><span data-stu-id="c1547-106">Create a policy</span></span>
1. <span data-ttu-id="c1547-107">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady akumulacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="c1547-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c1547-108">Click New.</span></span>
3. <span data-ttu-id="c1547-109">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="c1547-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c1547-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c1547-111">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-112">Wybierz centrum kosztów Akumulacja kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="c1547-113">W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-114">Wybierz centrum kosztów Akumulacja kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="c1547-115">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c1547-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="c1547-116">Tworzenie reguł dla zasady akumulacji kosztów</span><span class="sxs-lookup"><span data-stu-id="c1547-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="c1547-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c1547-117">Click New.</span></span>
2. <span data-ttu-id="c1547-118">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c1547-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="c1547-119">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-120">Wybierz pozycję 007.</span><span class="sxs-lookup"><span data-stu-id="c1547-120">Select 007.</span></span>  
4. <span data-ttu-id="c1547-121">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-122">Wybierz składnik kosztu Akumulacja kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="c1547-123">W polu Podrzędny składnik kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-124">W tym przykładzie należy zamapować podrzędny składnik kosztu CC-007 na centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="c1547-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c1547-125">Click New.</span></span>
7. <span data-ttu-id="c1547-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c1547-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="c1547-127">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-128">Wybierz pozycję 008.</span><span class="sxs-lookup"><span data-stu-id="c1547-128">Select 008.</span></span>  
9. <span data-ttu-id="c1547-129">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-130">Wybierz składnik kosztu Akumulacja kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="c1547-131">W polu Podrzędny składnik kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-132">W tym przykładzie należy zamapować podrzędny składnik kosztu CC-008 na centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="c1547-133">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c1547-133">Click New.</span></span>
12. <span data-ttu-id="c1547-134">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c1547-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="c1547-135">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-136">Wybierz pozycję 009.</span><span class="sxs-lookup"><span data-stu-id="c1547-136">Select 009.</span></span>  
14. <span data-ttu-id="c1547-137">W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-138">Wybierz składnik kosztu Akumulacja kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="c1547-139">W polu Podrzędny składnik kosztu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1547-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="c1547-140">W tym przykładzie należy zamapować podrzędny składnik kosztu CC-009 na centrum kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="c1547-141">Kontynuuj, aż wszystkie centra kosztów zostaną zamapowane na ich odnośne podrzędne składniki kosztów.</span><span class="sxs-lookup"><span data-stu-id="c1547-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="c1547-142">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c1547-142">Click Save.</span></span>

