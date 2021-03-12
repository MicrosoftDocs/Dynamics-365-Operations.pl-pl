---
title: Tworzenie planu materiałów dla produktów towarzyszących
description: Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8e9067cdd8851da31c07a92217001e447f400d4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983398"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="cfddf-103">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="cfddf-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cfddf-104">Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.</span><span class="sxs-lookup"><span data-stu-id="cfddf-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="cfddf-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="cfddf-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="cfddf-106">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="cfddf-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="cfddf-107">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="cfddf-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="cfddf-108">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="cfddf-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="cfddf-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cfddf-109">Click New.</span></span>
4. <span data-ttu-id="cfddf-110">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cfddf-110">Click Sales order.</span></span>
5. <span data-ttu-id="cfddf-111">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="cfddf-112">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="cfddf-112">Example: US-001</span></span>  
6. <span data-ttu-id="cfddf-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cfddf-113">Click OK.</span></span>
7. <span data-ttu-id="cfddf-114">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="cfddf-115">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="cfddf-115">Example: P6003</span></span>  
8. <span data-ttu-id="cfddf-116">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="cfddf-117">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="cfddf-117">Example: 50000</span></span>  
9. <span data-ttu-id="cfddf-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cfddf-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="cfddf-119">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="cfddf-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="cfddf-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cfddf-120">Close the page.</span></span>
2. <span data-ttu-id="cfddf-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cfddf-121">Close the page.</span></span>
3. <span data-ttu-id="cfddf-122">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="cfddf-122">Click Master planning.</span></span>
4. <span data-ttu-id="cfddf-123">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="cfddf-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="cfddf-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfddf-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cfddf-125">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="cfddf-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="cfddf-126">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="cfddf-126">Click Run.</span></span>
7. <span data-ttu-id="cfddf-127">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="cfddf-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="cfddf-128">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="cfddf-128">Click Filter.</span></span>
9. <span data-ttu-id="cfddf-129">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="cfddf-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="cfddf-130">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="cfddf-131">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="cfddf-131">Example: P6003</span></span>  
11. <span data-ttu-id="cfddf-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cfddf-132">Click OK.</span></span>
12. <span data-ttu-id="cfddf-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cfddf-133">Click OK.</span></span>
13. <span data-ttu-id="cfddf-134">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="cfddf-134">Click Planned orders.</span></span>
14. <span data-ttu-id="cfddf-135">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="cfddf-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="cfddf-136">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="cfddf-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="cfddf-137">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cfddf-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="cfddf-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cfddf-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cfddf-139">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="cfddf-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="cfddf-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfddf-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="cfddf-141">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="cfddf-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="cfddf-142">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfddf-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cfddf-143">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="cfddf-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="cfddf-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cfddf-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="cfddf-145">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="cfddf-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="cfddf-146">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="cfddf-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="cfddf-147">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="cfddf-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="cfddf-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="cfddf-148">Click New.</span></span>
4. <span data-ttu-id="cfddf-149">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cfddf-149">Click Sales order.</span></span>
5. <span data-ttu-id="cfddf-150">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="cfddf-151">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="cfddf-151">Example: US-001</span></span>  
6. <span data-ttu-id="cfddf-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cfddf-152">Click OK.</span></span>
7. <span data-ttu-id="cfddf-153">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="cfddf-154">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="cfddf-154">Example: P6003</span></span>  
8. <span data-ttu-id="cfddf-155">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="cfddf-156">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="cfddf-156">Example: 50000</span></span>  
9. <span data-ttu-id="cfddf-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="cfddf-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="cfddf-158">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="cfddf-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="cfddf-159">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="cfddf-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="cfddf-160">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfddf-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cfddf-161">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="cfddf-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="cfddf-162">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="cfddf-162">Click Run.</span></span>
4. <span data-ttu-id="cfddf-163">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="cfddf-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="cfddf-164">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="cfddf-164">Click Filter.</span></span>
6. <span data-ttu-id="cfddf-165">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="cfddf-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="cfddf-166">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="cfddf-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="cfddf-167">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="cfddf-167">Example: P6003</span></span>  
8. <span data-ttu-id="cfddf-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cfddf-168">Click OK.</span></span>
9. <span data-ttu-id="cfddf-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="cfddf-169">Click OK.</span></span>
10. <span data-ttu-id="cfddf-170">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="cfddf-170">Click Planned orders.</span></span>
11. <span data-ttu-id="cfddf-171">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="cfddf-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="cfddf-172">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="cfddf-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="cfddf-173">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cfddf-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="cfddf-174">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="cfddf-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cfddf-175">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="cfddf-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="cfddf-176">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfddf-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="cfddf-177">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="cfddf-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="cfddf-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="cfddf-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cfddf-179">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="cfddf-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="cfddf-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cfddf-180">Close the page.</span></span>
17. <span data-ttu-id="cfddf-181">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="cfddf-181">Click Master planning.</span></span>
18. <span data-ttu-id="cfddf-182">Wybierz kolejno opcje Planowanie główne > Ustawienia > Parametry planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="cfddf-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="cfddf-183">W polu Wyłącz wszystkie procesy planowania wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="cfddf-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="cfddf-184">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="cfddf-184">Close the page.</span></span>

