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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14de9a1085ac1cae88ad93c35385dd43c60ed4d1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982216"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="9e615-103">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="9e615-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e615-104">Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.</span><span class="sxs-lookup"><span data-stu-id="9e615-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="9e615-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="9e615-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="9e615-106">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="9e615-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="9e615-107">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="9e615-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="9e615-108">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="9e615-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="9e615-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9e615-109">Click New.</span></span>
4. <span data-ttu-id="9e615-110">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9e615-110">Click Sales order.</span></span>
5. <span data-ttu-id="9e615-111">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9e615-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="9e615-112">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="9e615-112">Example: US-001</span></span>  
6. <span data-ttu-id="9e615-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9e615-113">Click OK.</span></span>
7. <span data-ttu-id="9e615-114">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9e615-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="9e615-115">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="9e615-115">Example: P6003</span></span>  
8. <span data-ttu-id="9e615-116">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="9e615-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="9e615-117">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="9e615-117">Example: 50000</span></span>  
9. <span data-ttu-id="9e615-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9e615-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="9e615-119">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="9e615-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="9e615-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9e615-120">Close the page.</span></span>
2. <span data-ttu-id="9e615-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9e615-121">Close the page.</span></span>
3. <span data-ttu-id="9e615-122">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="9e615-122">Click Master planning.</span></span>
4. <span data-ttu-id="9e615-123">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9e615-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9e615-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9e615-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9e615-125">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="9e615-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="9e615-126">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="9e615-126">Click Run.</span></span>
7. <span data-ttu-id="9e615-127">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="9e615-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="9e615-128">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="9e615-128">Click Filter.</span></span>
9. <span data-ttu-id="9e615-129">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="9e615-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="9e615-130">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9e615-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="9e615-131">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="9e615-131">Example: P6003</span></span>  
11. <span data-ttu-id="9e615-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9e615-132">Click OK.</span></span>
12. <span data-ttu-id="9e615-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9e615-133">Click OK.</span></span>
13. <span data-ttu-id="9e615-134">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="9e615-134">Click Planned orders.</span></span>
14. <span data-ttu-id="9e615-135">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="9e615-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9e615-136">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="9e615-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="9e615-137">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9e615-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="9e615-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9e615-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9e615-139">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="9e615-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="9e615-140">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9e615-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="9e615-141">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="9e615-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="9e615-142">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9e615-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9e615-143">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="9e615-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="9e615-144">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9e615-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="9e615-145">Tworzenie zapotrzebowania na produkt towarzyszący</span><span class="sxs-lookup"><span data-stu-id="9e615-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="9e615-146">Przejdź do domyślnego pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="9e615-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="9e615-147">Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.</span><span class="sxs-lookup"><span data-stu-id="9e615-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="9e615-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="9e615-148">Click New.</span></span>
4. <span data-ttu-id="9e615-149">Kliknij opcję zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9e615-149">Click Sales order.</span></span>
5. <span data-ttu-id="9e615-150">W polu Konto odbiorcy wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9e615-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="9e615-151">Przykład: US-001</span><span class="sxs-lookup"><span data-stu-id="9e615-151">Example: US-001</span></span>  
6. <span data-ttu-id="9e615-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9e615-152">Click OK.</span></span>
7. <span data-ttu-id="9e615-153">W polu Numer towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9e615-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="9e615-154">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="9e615-154">Example: P6003</span></span>  
8. <span data-ttu-id="9e615-155">Wprowadź liczbę w polu Ilość.</span><span class="sxs-lookup"><span data-stu-id="9e615-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="9e615-156">Przykład: 50000</span><span class="sxs-lookup"><span data-stu-id="9e615-156">Example: 50000</span></span>  
9. <span data-ttu-id="9e615-157">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9e615-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="9e615-158">Tworzenie planu materiałów dla produktów towarzyszących</span><span class="sxs-lookup"><span data-stu-id="9e615-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="9e615-159">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="9e615-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="9e615-160">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9e615-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9e615-161">Przykład: Plan główny</span><span class="sxs-lookup"><span data-stu-id="9e615-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="9e615-162">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="9e615-162">Click Run.</span></span>
4. <span data-ttu-id="9e615-163">Rozwiń lub zwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="9e615-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="9e615-164">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="9e615-164">Click Filter.</span></span>
6. <span data-ttu-id="9e615-165">Na liście zaznacz wiersz, gdzie Pole = Numer towaru.</span><span class="sxs-lookup"><span data-stu-id="9e615-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="9e615-166">W polu Kryteria wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9e615-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="9e615-167">Przykład: P6003</span><span class="sxs-lookup"><span data-stu-id="9e615-167">Example: P6003</span></span>  
8. <span data-ttu-id="9e615-168">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9e615-168">Click OK.</span></span>
9. <span data-ttu-id="9e615-169">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9e615-169">Click OK.</span></span>
10. <span data-ttu-id="9e615-170">Kliknij opcję Zamówienia planowane.</span><span class="sxs-lookup"><span data-stu-id="9e615-170">Click Planned orders.</span></span>
11. <span data-ttu-id="9e615-171">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="9e615-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9e615-172">Na przykład wyfiltruj według pola Numer towaru z wartością „6000”.</span><span class="sxs-lookup"><span data-stu-id="9e615-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="9e615-173">Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9e615-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="9e615-174">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9e615-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9e615-175">Wybierz dowolny wiersz zwrócony przez filtr.</span><span class="sxs-lookup"><span data-stu-id="9e615-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="9e615-176">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9e615-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="9e615-177">Rozwiń lub zwiń sekcję Oznaczanie transakcji.</span><span class="sxs-lookup"><span data-stu-id="9e615-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="9e615-178">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9e615-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9e615-179">Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.</span><span class="sxs-lookup"><span data-stu-id="9e615-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="9e615-180">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9e615-180">Close the page.</span></span>
17. <span data-ttu-id="9e615-181">Kliknij opcję Planowanie główne.</span><span class="sxs-lookup"><span data-stu-id="9e615-181">Click Master planning.</span></span>
18. <span data-ttu-id="9e615-182">Wybierz kolejno opcje Planowanie główne > Ustawienia > Parametry planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="9e615-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="9e615-183">W polu Wyłącz wszystkie procesy planowania wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="9e615-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="9e615-184">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="9e615-184">Close the page.</span></span>

