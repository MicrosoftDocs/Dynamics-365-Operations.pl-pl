--- 
title: "Tworzenie planu materiałów dla produktów towarzyszących"
description: "Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="0829b-103">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="0829b-103">Create a material plan for co-products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0829b-104">Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.</span><span class="sxs-lookup"><span data-stu-id="0829b-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="0829b-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="0829b-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="0829b-106">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="0829b-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="0829b-107">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="0829b-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="0829b-108">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="0829b-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="0829b-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="0829b-109">Click New.</span></span>
4. <span data-ttu-id="0829b-110">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0829b-110">Click Sales order.</span></span>
5. <span data-ttu-id="0829b-111">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0829b-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="0829b-112">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="0829b-112">Example: US-001</span></span>  
6. <span data-ttu-id="0829b-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0829b-113">Click OK.</span></span>
7. <span data-ttu-id="0829b-114">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0829b-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="0829b-115">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="0829b-115">Example: P6003</span></span>  
8. <span data-ttu-id="0829b-116">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="0829b-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0829b-117">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="0829b-117">Example: 50000</span></span>  
9. <span data-ttu-id="0829b-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="0829b-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="0829b-119">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="0829b-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="0829b-120">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="0829b-120">Click Master planning.</span></span>
2. <span data-ttu-id="0829b-121">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0829b-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="0829b-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0829b-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0829b-123">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="0829b-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="0829b-124">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="0829b-124">Click Run.</span></span>
5. <span data-ttu-id="0829b-125">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="0829b-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="0829b-126">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="0829b-126">Click Filter.</span></span>
7. <span data-ttu-id="0829b-127">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="0829b-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="0829b-128">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0829b-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="0829b-129">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="0829b-129">Example: P6003</span></span>  
9. <span data-ttu-id="0829b-130">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0829b-130">Click OK.</span></span>
10. <span data-ttu-id="0829b-131">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0829b-131">Click OK.</span></span>
11. <span data-ttu-id="0829b-132">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="0829b-132">Click Planned orders.</span></span>
12. <span data-ttu-id="0829b-133">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="0829b-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0829b-134">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="0829b-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="0829b-135">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0829b-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="0829b-136">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="0829b-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0829b-137">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="0829b-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="0829b-138">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0829b-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="0829b-139">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="0829b-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="0829b-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0829b-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0829b-141">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="0829b-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="0829b-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0829b-142">Close the page.</span></span>


